# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/c8c2813d-4797-4969-b335-b2cd2bc11e30/original)](https://ampli-images.s3.amazonaws.com/production/c8c2813d-4797-4969-b335-b2cd2bc11e30/original)

### **Qual é o foco da aula?**

Nesta aula, você irá aprender formatação de tabelas e formulários.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- apontar _frameworks_ CSS e _JavaScript_;
- nomear _DataTables_ e _Bootstrap_;
- descrever animações utilizando CSS.

**Situação-problema**

Olá!

Nesta aula, daremos continuidade ao uso das folhas de estilo em cascata. Desta vez, você aprenderá os fundamentos para formatação de estilos para tabelas e formulários.

Apesar de ser um recurso oriundo das primeiras versões do HTML, as tabelas ainda são utilizadas em muitas aplicações, em especial, para exibição de conteúdo tabular. A principal diferença é que as alterações nos estilos, como bordas e cores, eram realizadas por meio de atributos das _tags_. Nos dias de hoje, convencionou-se que a melhor maneira de alterar estilos tanto em tabelas quanto em qualquer elemento HTML é por meio das propriedades CSS. Aqui, aplicaremos propriedades CSS de bordas, margens e cores de fundo em tabelas e formulários.

Nesta aula, você também será introduzido ao maravilhoso mundo dos _frameworks_ CSS/_JavaScript_, que são bibliotecas de códigos com inúmeras funcionalidades já desenvolvidas e testadas por muitos outros desenvolvedores. Por meio de um _framework_ é possível aplicar diversas configurações de estilos apenas inserindo o nome das classes; além disso, ele permite que desenvolvedores criem aplicações com interface amigável utilizando-se poucas linhas de código.

Você vai conhecer dois frameworks: _DataTables_, uma biblioteca especialmente construída para formatação de tabelas, e _Bootstrap_, um _framework_ CSS+JavaScript com inúmeras funcionalidades de estilo, como formatação de formulários e tabelas, definição da grade de estrutura de uma página, entre outras.

Por fim, você será introduzido ao mundo das animações utilizando apenas a linguagem CSS. As propriedades de animação permitem transitar entre um estilo e outro. Animações em CSS, apesar de serem mais simples quando comparadas com _JavaScrip_t, permitem tornar a página mais dinâmica com um baixo custo para carregamento pelo navegador.

Na empresa em que trabalha, você foi requisitado a implementar as outras páginas remanescentes para compor a página WEB.

- Página inicial.
- Página “quem somos”.
- Página “produtos”.

Entretanto, nessa nova implementação, alguns requisitos são importantes:

1. Sua página deve apresentar design responsivo.
2. Use o _lorem ipsum_ para preencher a página quem somos; imagens podem ser coletadas no _Pixabay_.
3. Opcionalmente, você pode criar uma página única em que cada uma corresponda a uma seção dessa página principal (use _links_ de navegação interna).
4. Na página “produtos”, os itens apresentados da figura abaixo devem estar inclusos.

[![](https://ampli-images.s3.amazonaws.com/production/d68657e6-c9ea-4509-8a23-ccd77b278be5/original)](https://ampli-images.s3.amazonaws.com/production/d68657e6-c9ea-4509-8a23-ccd77b278be5/original)

Itens a serem inclusos na página produtos. Fonte: elaborado pelo autor.

**⭐ Dica**

Você pode usar o _Bootstrap_ e o _DataTables_ em sua página.

______

Os conhecimentos apresentados nesta aula poderão representar um grande avanço em sua carreira de desenvolvedor web, por isso, foco total e bons estudos!

# **Conceito-chave**

[![](https://ampli-images.s3.amazonaws.com/production/f7f64896-b42a-4af6-8a96-6d21fc3d9f17/original)](https://ampli-images.s3.amazonaws.com/production/f7f64896-b42a-4af6-8a96-6d21fc3d9f17/original)

Estudante, nesta aula, você aprenderá a aplicar estilos em tabelas e formulários. Nas primeiras versões do HTML, estilos eram aplicados com o conteúdo, o que dificultava a manutenção e a escalabilidade do código. Com as aplicações CSS, foi possível separar códigos de conteúdos e códigos de estilo, e os estilos podem ser aplicados a todas as tabelas e formulários de uma página web.

O foco principal desta aula será apresentar estilos para tabelas, mas muitas das propriedades aplicadas a tabelas também podem ser aplicadas a formulários. Além disso, muitas dessas propriedades já foram apresentadas anteriormente para outros elementos CSS. Por fim, você vai conhecer dois poderosos _frameworks_ CSS para inserção de estilos automáticos: _DataTables_ e _Bootstrap_. Os frameworks reduzem consideravelmente a quantidade de código necessária para construção de páginas com layout amigável. Você verá que, conhecendo fundamentos básicos desses _frameworks_, já é possível construir belas páginas.

Para ilustrarmos o conteúdo apresentado, vamos utilizar os dados da população brasileira do ano de 2017:

[![](https://ampli-images.s3.amazonaws.com/production/588cbf4b-72d4-452f-a81d-e8eec54ac57e/original)](https://ampli-images.s3.amazonaws.com/production/588cbf4b-72d4-452f-a81d-e8eec54ac57e/original)

[![](https://ampli-images.s3.amazonaws.com/production/4c40d3b1-1c24-4ed0-9f83-33d232fe1934/original)](https://ampli-images.s3.amazonaws.com/production/4c40d3b1-1c24-4ed0-9f83-33d232fe1934/original)

[![](https://ampli-images.s3.amazonaws.com/production/d9393483-136c-4f70-96eb-d21c121742da/original)](https://ampli-images.s3.amazonaws.com/production/d9393483-136c-4f70-96eb-d21c121742da/original)

[![](https://ampli-images.s3.amazonaws.com/production/131b55eb-7ca7-4bbd-a687-48ee41329b7d/original)](https://ampli-images.s3.amazonaws.com/production/131b55eb-7ca7-4bbd-a687-48ee41329b7d/original)

População do Brasil por estados. Fonte:adaptado de SILVEIRA (2017).

# **Elementos da tabela**

[![](https://ampli-images.s3.amazonaws.com/production/72548cd1-b179-404d-995d-0d517824de6d/original)](https://ampli-images.s3.amazonaws.com/production/72548cd1-b179-404d-995d-0d517824de6d/original)

Por padrão, navegadores não aplicam qualquer formatação, exibindo a tabela em branco. Logo, se recriarmos a tabela acima em HTML, ela ficará assim:

[![](https://ampli-images.s3.amazonaws.com/production/5d18ff79-8c42-4ec0-8243-6b2947b10d46/original)](https://ampli-images.s3.amazonaws.com/production/5d18ff79-8c42-4ec0-8243-6b2947b10d46/original)

Visualização da tabela criada em HTML. Fonte: elaborada pelo autor.

Podemos aplicar estilos a tabelas usando as _tags_ internas de tabelas. Uma tabela é composta por elementos como na figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/fe3a4008-020e-47ea-ac88-6ac0cca68fff/original)](https://ampli-images.s3.amazonaws.com/production/fe3a4008-020e-47ea-ac88-6ac0cca68fff/original)

Tags de tabelas. Fonte: elaborada pelo autor.

Por exemplo, podemos aplicar uma borda aplicando a propriedade:

[![](https://ampli-images.s3.amazonaws.com/production/600ac766-3fbf-4647-bd45-173628826453/original)](https://ampli-images.s3.amazonaws.com/production/600ac766-3fbf-4647-bd45-173628826453/original)

O resultado ficará da seguinte forma:

[![](https://ampli-images.s3.amazonaws.com/production/9edc1fc8-9f8a-46b8-a112-f630657a43b5/original)](https://ampli-images.s3.amazonaws.com/production/9edc1fc8-9f8a-46b8-a112-f630657a43b5/original)

Tabela com bordas. Fonte: elaborada pelo autor.

Note que também aplicamos uma margem interna de 10px. Por padrão, tabelas não apresentam margens internas, o que pode dificultar a leitura.

Perceba, ainda, que cada célula possui um espaçamento que gera um efeito de borda dupla. Podemos remover isso usando a propriedade “_border-colapse_” (“_A Complete Guide to the Table Element_”, 2013). Veja:

[![](https://ampli-images.s3.amazonaws.com/production/ceb95dd2-d514-422c-9940-83b3a5869451/original)](https://ampli-images.s3.amazonaws.com/production/ceb95dd2-d514-422c-9940-83b3a5869451/original)

Por fim, podemos, também, adicionar detalhes ao nosso cabeçalho _(tag_ ), como inverter a cor de fundo e de texto:

[![](https://ampli-images.s3.amazonaws.com/production/25565c28-89ac-4235-8b75-b935274d39d9/original)](https://ampli-images.s3.amazonaws.com/production/25565c28-89ac-4235-8b75-b935274d39d9/original)

Veja que declaramos **th** duas vezes (na primeira vez, foram aplicadas regras à **td** e **th**, mas abaixo, apenas à **th**. Não há qualquer problema em fazer múltiplas declarações a um elemento CSS; deve-se, apenas, ressaltar que o efeito cascata garante que, caso haja duas declarações idênticas, a última declaração realizada se sobreponha à outra (exceto se a expressão **!important** for usada).

A figura abaixo ilustra a tabela resultante.

[![](https://ampli-images.s3.amazonaws.com/production/08c2277d-b759-4134-9e31-dcf91c3fd2cd/original)](https://ampli-images.s3.amazonaws.com/production/08c2277d-b759-4134-9e31-dcf91c3fd2cd/original)

[![](https://ampli-images.s3.amazonaws.com/production/09e4c582-f22e-4c3d-b480-3e80dff1be2a/original)](https://ampli-images.s3.amazonaws.com/production/09e4c582-f22e-4c3d-b480-3e80dff1be2a/original)

Aplicando estilos a uma tabela com CSS. Fonte: elaborada pelo autor.

# **Formatação de dados da tabela**

[![](https://ampli-images.s3.amazonaws.com/production/d92e50b3-009c-4bc4-8204-876716f87179/original)](https://ampli-images.s3.amazonaws.com/production/d92e50b3-009c-4bc4-8204-876716f87179/original)

Note, pelos exemplos anteriores, que a formatação de tabelas pode demandar bastante tempo, uma vez que requer que você aplique diversas regras individualmente, visando facilitar a leitura dos dados na tabela. Algumas das regras apresentadas parecem simples e repetitivas (como as regras de inserção de bordas para a tabela), logo, pode-se observar que não é necessário reimplementar essas mesmas regras em toda a página HTML criada. Por isso, surgiram os chamados _frameworks_ CSS, que facilitam a construção de sites fornecendo uma série de componentes básicos para formatação de _layouts_ amigáveis usando-se poucas linhas de códigos.

______

🔁 **Assimile**

**O que é um** _**framework**_**?**

Em computação, um _framework_ é um conjunto de códigos que contém uma série de funcionalidades pré-desenvolvidas. O objetivo de um _framework_ é facilitar o desenvolvimento de projetos de _software_ mais completos, reduzindo o tempo gasto para se codificar funcionalidades básicas.

______

Um exemplo de _framework_ voltado exclusivamente para criação de tabelas é o _DataTables_.

# **Datatables**

[![](https://ampli-images.s3.amazonaws.com/production/c5cf6de5-ddb1-43f8-b7eb-c31f47363dbb/original)](https://ampli-images.s3.amazonaws.com/production/c5cf6de5-ddb1-43f8-b7eb-c31f47363dbb/original)

_DataTables_ é um _framework_ CSS/_JavaScript_ especialmente desenvolvido para formatação automática de tabelas. Ele contém funcionalidades avançadas que podem ser inseridas com poucas linhas de código, bem como permite, por exemplo, a ordenação alfabética ou numérica de dados da tabela com base em elementos de uma coluna, a busca em dados de uma tabela e a paginação de dados exibidos na tabela. A única desvantagem do _DataTables_ é que a interface da tabela é configurada em inglês (ex.: o botão de busca aparece como “search”). Isso não é algo que compromete o uso, mas, como desenvolvedores web, devemos sempre focar em apresentar interfaces amigáveis e compreensíveis para todos os usuários. Além disso, para usuários avançados, é possível personalizar as mensagens.

______

**⭐ Dica**

**Usando o DataTables**

A implementação do _DataTables_ é bastante simples. Você pode fazer o _download_ dele no site. Há várias versões disponíveis (mas apresentaremos apenas a versão básica). Precisaremos, apenas, de dois arquivos: query.dataTables.min.css e jquery.dataTables.min.js, bem como do jQuery (falaremos mais sobre ele no capítulo de _JavaScript_).

Caso não consiga fazer o _download_ dos arquivos, mostraremos, a seguir, como fazer uma instalação usando a CDN (_Content Delivery Network_ ou, na tradução, Rede de Fornecimento de Conteúdo). Com a CDN, não é necessário baixar os arquivos, basta utilizar os links disponibilizados pelos servidores (requer conexão com a internet). Para isso, serão necessários apenas três passos:

1. Inserção do estilo CSS: entre as _tags <head> </head_> inclua o seguinte código:

[![](https://ampli-images.s3.amazonaws.com/production/2b7589f9-9bd0-422a-9924-75a87155c192/original)](https://ampli-images.s3.amazonaws.com/production/2b7589f9-9bd0-422a-9924-75a87155c192/original)

2. Inserção dos arquivos JavaScript do jQuery e do _DataTables_ entre as _tags <footer> </footer>_ (ou seja, no fim da página):

[![](https://ampli-images.s3.amazonaws.com/production/5da3b7ac-ea5b-4e6c-a3e2-b2c9abaa2c41/original)](https://ampli-images.s3.amazonaws.com/production/5da3b7ac-ea5b-4e6c-a3e2-b2c9abaa2c41/original)

3. Código de ativação da tabela com base no ID (deve ser inserido depois da declaração do _script_ anterior):

[![](https://ampli-images.s3.amazonaws.com/production/8afe31b7-35b5-4f55-be35-b228c1cf6d42/original)](https://ampli-images.s3.amazonaws.com/production/8afe31b7-35b5-4f55-be35-b228c1cf6d42/original)

**Importante**: altere o valor “\#nome-tabela” pelo ID que você deu a sua tabela.

Após a configuração do _DataTables_, note que que foi incluído na linha 6 o seguinte código:

[![](https://ampli-images.s3.amazonaws.com/production/a0ce9412-08a6-4a3b-97a7-cf8c746b42ca/original)](https://ampli-images.s3.amazonaws.com/production/a0ce9412-08a6-4a3b-97a7-cf8c746b42ca/original)

Agora, compare as diferenças das duas versões, uma tabela construída com o estilo nativo do navegador e uma tabela construída com o estilo nativo do _DataTables_:

[![](https://ampli-images.s3.amazonaws.com/production/587b3dba-84a7-414c-8898-fe05ed373fbf/original)](https://ampli-images.s3.amazonaws.com/production/587b3dba-84a7-414c-8898-fe05ed373fbf/original)

[![](https://ampli-images.s3.amazonaws.com/production/3950628a-9198-4e35-adcf-bf09103935b7/original)](https://ampli-images.s3.amazonaws.com/production/3950628a-9198-4e35-adcf-bf09103935b7/original)

[![](https://ampli-images.s3.amazonaws.com/production/cb368e15-4d27-48c4-b366-b643aa9bd284/original)](https://ampli-images.s3.amazonaws.com/production/cb368e15-4d27-48c4-b366-b643aa9bd284/original)

[![](https://ampli-images.s3.amazonaws.com/production/5dc0c5f5-f801-4bc9-a3c1-733b160773c2/original)](https://ampli-images.s3.amazonaws.com/production/5dc0c5f5-f801-4bc9-a3c1-733b160773c2/original)

Diferença do estilo padrão do navegador (A) e do estilo padrão do DataTables (B). Fonte: elaborada pelo autor.

Observe que _DataTables_ inseriu uma linha divisória de cabeçalho, uma barra de buscas e de paginação, além dos mecanismos de ordenação.

[![](https://ampli-images.s3.amazonaws.com/production/7b3d499d-d55b-4b96-86fd-df5f15479a64/original)](https://ampli-images.s3.amazonaws.com/production/7b3d499d-d55b-4b96-86fd-df5f15479a64/original)

Detalhes da tabela padrão do DataTables. Fonte: elaborada pelo autor.

E tudo isso foi realizado com poucas linhas de códigos.

______

Agora, veremos outro _framework_ CSS bastante popular: _Bootstrap_.

# **Bootstrap**

[![](https://ampli-images.s3.amazonaws.com/production/e15f3cb0-c6b4-4141-bbb9-429ddf0fa071/original)](https://ampli-images.s3.amazonaws.com/production/e15f3cb0-c6b4-4141-bbb9-429ddf0fa071/original)

Bootstrap é um _framework_ CSS/_JavaScript_ que contém funcionalidades generalizadas para diversos elementos HTML, como tabelas, formulários, botões, textos, entre muitos outros. Entre os muitos recursos do _Bootstrap_, estão as funcionalidades de construção de páginas responsivas, que são compatíveis com celulares, computadores e tablets.

Assim como _DataTables_, o _Bootstrap_ pode ser executado via CDN. Para isso, basta inserir os seguintes códigos em sua página:

1. Folhas CSS entre as _tags_ <_head> </head_>

[![](https://ampli-images.s3.amazonaws.com/production/4afa1476-07f7-442b-94a0-b7f1b52d002d/original)](https://ampli-images.s3.amazonaws.com/production/4afa1476-07f7-442b-94a0-b7f1b52d002d/original)

2. Arquivos _JavaScript_ entre as _tags_ <footer> </footer> (requer jQuery):

[![](https://ampli-images.s3.amazonaws.com/production/03a92798-60d7-4773-b5a0-0a1b7ac1e3dc/original)](https://ampli-images.s3.amazonaws.com/production/03a92798-60d7-4773-b5a0-0a1b7ac1e3dc/original)

_Bootstrap_ é executado por meio de classes atribuídas. Por exemplo, uma formatação simples de tabelas pode ser feita atribuindo-se a classe “_table_”:

[![](https://ampli-images.s3.amazonaws.com/production/2638d700-d3df-4339-afae-3ec01f95f32d/original)](https://ampli-images.s3.amazonaws.com/production/2638d700-d3df-4339-afae-3ec01f95f32d/original)

A figura abaixo apresenta a Tabela padrão do _Bootstrap_. Veja o resultado do exemplo da tabela apresentada anteriormente.

[![](https://ampli-images.s3.amazonaws.com/production/58d0a253-6a98-4435-9f27-9831dfb4d7e3/original)](https://ampli-images.s3.amazonaws.com/production/58d0a253-6a98-4435-9f27-9831dfb4d7e3/original)

[![](https://ampli-images.s3.amazonaws.com/production/f7fac7fd-0eae-4a56-88b9-eae53cae87c2/original)](https://ampli-images.s3.amazonaws.com/production/f7fac7fd-0eae-4a56-88b9-eae53cae87c2/original)

Tabela padrão do Bootstrap. Fonte: elaborada pelo autor.

Entretanto, o _Bootstrap_ oferece uma série de classes que podem ser aplicadas em conjunto com a classe _table_ para se formatar tabelas. É possível utilizar as seguintes classes (Tabela 3):

[![](https://ampli-images.s3.amazonaws.com/production/43751155-6785-4535-8cb5-bfd49075a413/original)](https://ampli-images.s3.amazonaws.com/production/43751155-6785-4535-8cb5-bfd49075a413/original)

Classes para formatação de tabelas do Bootstrap. Fonte: elaborada pelo autor.

A figura a seguir apresenta alguns exemplos de uso das classes apresentadas na tabela anterior para a tabela de população brasileira estratificada por estados:

[![](https://ampli-images.s3.amazonaws.com/production/72afc4ec-50a3-4346-9c6c-59ea4686a948/original)](https://ampli-images.s3.amazonaws.com/production/72afc4ec-50a3-4346-9c6c-59ea4686a948/original)

[![](https://ampli-images.s3.amazonaws.com/production/60c0a07a-c520-4af1-b916-6457f9c3ed2d/original)](https://ampli-images.s3.amazonaws.com/production/60c0a07a-c520-4af1-b916-6457f9c3ed2d/original)

[![](https://ampli-images.s3.amazonaws.com/production/0c6cc989-d763-4804-a3d8-9c818a1afc15/original)](https://ampli-images.s3.amazonaws.com/production/0c6cc989-d763-4804-a3d8-9c818a1afc15/original)

[![](https://ampli-images.s3.amazonaws.com/production/2b9f2e9a-48b7-41e2-96f0-d76202031503/original)](https://ampli-images.s3.amazonaws.com/production/2b9f2e9a-48b7-41e2-96f0-d76202031503/original)

[![](https://ampli-images.s3.amazonaws.com/production/fb92f5fd-05ab-465c-9fe8-8817be879613/original)](https://ampli-images.s3.amazonaws.com/production/fb92f5fd-05ab-465c-9fe8-8817be879613/original)

[![](https://ampli-images.s3.amazonaws.com/production/3a1d6015-e8ef-4b37-b44c-4dd88becffa9/original)](https://ampli-images.s3.amazonaws.com/production/3a1d6015-e8ef-4b37-b44c-4dd88becffa9/original)

Linhas coloridas. Fonte: elaborada pelo autor.

Você pode, ainda, aplicar cores às linhas usando as propriedades de cores. Observe o resultado:

[![](https://ampli-images.s3.amazonaws.com/production/ded79322-3c32-42a4-9c5b-67b6ddbc6b48/original)](https://ampli-images.s3.amazonaws.com/production/ded79322-3c32-42a4-9c5b-67b6ddbc6b48/original)

Linhas coloridas. Fonte: elaborada pelo autor.

Observe o código necessário para criar essa tabela:

[![](https://ampli-images.s3.amazonaws.com/production/09884bbb-b800-4626-a144-80dd3633bdbf/original)](https://ampli-images.s3.amazonaws.com/production/09884bbb-b800-4626-a144-80dd3633bdbf/original)

[![](https://ampli-images.s3.amazonaws.com/production/786c02ae-82fb-493d-bf5b-7e1c75070cce/original)](https://ampli-images.s3.amazonaws.com/production/786c02ae-82fb-493d-bf5b-7e1c75070cce/original)

[![](https://ampli-images.s3.amazonaws.com/production/9a9d1228-bc67-4c27-a4fd-dcd3c75ae57d/original)](https://ampli-images.s3.amazonaws.com/production/9a9d1228-bc67-4c27-a4fd-dcd3c75ae57d/original)

[![](https://ampli-images.s3.amazonaws.com/production/829ffcff-b217-470c-9c62-bacd6e260623/original)](https://ampli-images.s3.amazonaws.com/production/829ffcff-b217-470c-9c62-bacd6e260623/original)

[![](https://ampli-images.s3.amazonaws.com/production/4e03d5e4-5641-421d-9582-55a46f28fb66/original)](https://ampli-images.s3.amazonaws.com/production/4e03d5e4-5641-421d-9582-55a46f28fb66/original)

Criando uma tabela. Fonte: elaborada pelo autor.

**💭 Reflita**

O _Bootstrap_ utiliza classes para alterar as cores das linhas na tabela, e o seu uso é bastante simples e prático. Por exemplo: para a cor azul, utiliza-se a classe: _table-primary_.

Com base no código apresentado, quais seriam as classes utilizadas para colorir as linhas nas cores:

1. Cinza
2. Verde
3. Vermelho
4. Amarelo
5. Azul claro
6. Cinza claro
7. Cinza (texto branco)

# **Aplicando estilos CSS em formulários HTML**

[![](https://ampli-images.s3.amazonaws.com/production/8f3cfdac-4b56-4a87-ac97-7a9febc6e3a1/original)](https://ampli-images.s3.amazonaws.com/production/8f3cfdac-4b56-4a87-ac97-7a9febc6e3a1/original)

As mesmas propriedades CSS utilizadas para formatar tabelas também podem ser utilizadas em formulários.

Observe o seguinte formulário HTML:

[![](https://ampli-images.s3.amazonaws.com/production/a60edcb5-52e9-4d11-b7a2-4343da4c8aa5/original)](https://ampli-images.s3.amazonaws.com/production/a60edcb5-52e9-4d11-b7a2-4343da4c8aa5/original)

index.html. Fonte: elaborada pelo autor.

**⭐ Dica**

**Nota técnica**: o código apresenta apenas um fragmento do arquivo HTML. A fim de que não ficasse repetitivo, não exibimos _tags_ como <html>, <_head>, <body_>, <_footer_>, etc.; no entanto, muitas delas são essenciais, portanto, não se esqueça de inclui-las em seus códigos.

______

Agora, configuramos o arquivo CSS desta forma:

[![](https://ampli-images.s3.amazonaws.com/production/9cf70de8-3696-4869-bb6b-a083cee12547/original)](https://ampli-images.s3.amazonaws.com/production/9cf70de8-3696-4869-bb6b-a083cee12547/original)

[![](https://ampli-images.s3.amazonaws.com/production/7ce1173c-df19-4ba1-b5cc-827ea8fb5e0e/original)](https://ampli-images.s3.amazonaws.com/production/7ce1173c-df19-4ba1-b5cc-827ea8fb5e0e/original)

Estilo.css. Fonte: elaborada pelo autor.

Esse código irá produzir a seguinte página:

[![](https://ampli-images.s3.amazonaws.com/production/2218f405-f7c8-4adb-86a0-a53a8593945d/original)](https://ampli-images.s3.amazonaws.com/production/2218f405-f7c8-4adb-86a0-a53a8593945d/original)

Formulário com CSS. Fonte: elaborada pelo autor.

Agora, vamos entender as principais partes do código criado:

Nas linhas a seguir, foram aplicadas propriedades às _tags input_ (no caso, as caixas de inserção de textos).

[![](https://ampli-images.s3.amazonaws.com/production/eac12c7b-db46-452f-8dd8-3db76f71bb4b/original)](https://ampli-images.s3.amazonaws.com/production/eac12c7b-db46-452f-8dd8-3db76f71bb4b/original)

Veja que, nesse caso, apresentamos uma propriedade especial do CSS, _calc( )_, que é responsável por fazer um cálculo que determinará o tamanho ocupado pelo elemento. Trata-se de algo necessário, pois queremos que o _input_ ocupe toda a linha, mas sem ultrapassar os limites de largura estabelecidos. Nesse caso, ele ultrapassará os limites em 20px (10px à direita e 10px à esquerda), pois atribuímos, logo abaixo, uma margem interna de 10px (_padding_: 10px). Veja que os limites de largura não foram estabelecidos nesse elemento e sim na classe **container**:

[![](https://ampli-images.s3.amazonaws.com/production/c0bb2867-1414-4579-a1f6-7a12c6113ad5/original)](https://ampli-images.s3.amazonaws.com/production/c0bb2867-1414-4579-a1f6-7a12c6113ad5/original)

A mesma estratégia é aplicada para a _tag <textarea_>, que permite a inserção de blocos de texto de múltiplas linhas. Além disso, inserimos cada elemento do formulário em uma div e aplicamos a classe linha, que insere margens no topo (10px) e no rodapé (20px), entre cada um dos elementos adicionados:</div>

[![](https://ampli-images.s3.amazonaws.com/production/78c34b3a-335e-4c14-865c-8b7b681fa1fb/original)](https://ampli-images.s3.amazonaws.com/production/78c34b3a-335e-4c14-865c-8b7b681fa1fb/original)

Aplicamos, ainda, um estilo de cor no botão de submissão, por meio da classe “botao-enviar”.

[![](https://ampli-images.s3.amazonaws.com/production/9e472d0a-b32b-46f0-90ae-910a250547eb/original)](https://ampli-images.s3.amazonaws.com/production/9e472d0a-b32b-46f0-90ae-910a250547eb/original)

Nesse caso, aplicamos um tom de verde claro (código de cor hexadecimal \#02B81A) como cor de fundo e um tom de verde um pouco mais escuro (código de cor hexadecimal \#016B0F) como cor da borda, e isso foi feito para criarmos um efeito de contraste. Alteramos, ainda, a cor de fundo para branco e adicionamos uma margem interna de 20px para ampliar verticalmente o tamanho do botão. Por fim, para que o botão seguisse o mesmo estilo aplicado aos outros elementos, determinamos que ele ocupasse 100% do espaço destinado na página. Como usamos a classe container para delimitar sua ocupação, ele deverá ocupar 100% do elemento container, ou seja, 960px.

# **Formulários com Bootstrap**

[![](https://ampli-images.s3.amazonaws.com/production/2b7032c1-576a-49c6-a256-e3ba1273ccce/original)](https://ampli-images.s3.amazonaws.com/production/2b7032c1-576a-49c6-a256-e3ba1273ccce/original)

Você deve ter percebido que a modificação de estilos usando-se CSS envolve uma série de propriedades. Caso queira reduzir o tempo gasto no desenvolvimento, você pode utilizar as classes disponibilizadas pelo _Bootstrap_ para formatação de formulários. Observe o HTML a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/a9110fe4-c2b4-45dc-82ec-397d2fdb79a5/original)](https://ampli-images.s3.amazonaws.com/production/a9110fe4-c2b4-45dc-82ec-397d2fdb79a5/original)

index.html. Fonte: elaborada pelo autor.

Nesse caso, não precisaremos do arquivo “estilo.css”, portanto, substitua a declaração da sua folha de estilo pelo _Bootstrap_:

[![](https://ampli-images.s3.amazonaws.com/production/babcee45-69ba-4d29-8ed3-55b1b39522ec/original)](https://ampli-images.s3.amazonaws.com/production/babcee45-69ba-4d29-8ed3-55b1b39522ec/original)

O Código acima produzirá a seguinte página:

[![](https://ampli-images.s3.amazonaws.com/production/f84b402a-4a3b-4884-85ba-f8f9c3717627/original)](https://ampli-images.s3.amazonaws.com/production/f84b402a-4a3b-4884-85ba-f8f9c3717627/original)

Formulários com Bootstrap. Fonte: elaborada pelo autor.

Agora, você vai entender quais estilos e classes apresentadas aplicaram nos elementos CSS: **container, mt-4, form-control** e **btn**.

# **Container**

[![](https://ampli-images.s3.amazonaws.com/production/9f4856d5-ca00-4a58-9f8c-812b72f3c929/original)](https://ampli-images.s3.amazonaws.com/production/9f4856d5-ca00-4a58-9f8c-812b72f3c929/original)

O _Bootstrap_ também tem sua própria classe container. A vantagem dessa classe para o código que você criou manualmente é que o container do _Bootstrap_ é responsivo, i.e., logo, o bloco vai se ajustar de acordo com o dispositivo utilizado. Para ativar o design responsivo, você precisa incluir a seguinte meta _tag_ de escala dentro do <_head_>:

[![](https://ampli-images.s3.amazonaws.com/production/25cbc8b1-b1ce-49dc-a0ed-f651644c05b9/original)](https://ampli-images.s3.amazonaws.com/production/25cbc8b1-b1ce-49dc-a0ed-f651644c05b9/original)

Observe como a página construída sem e com _Bootstrap_ será vista em um smartphone:

[![](https://ampli-images.s3.amazonaws.com/production/e91a7f63-0adb-4806-8585-849d41361e31/original)](https://ampli-images.s3.amazonaws.com/production/e91a7f63-0adb-4806-8585-849d41361e31/original)

Comparação entre o container criado manualmente e o container nativo do Bootstrap. Fonte: elaborada pelo autor.

# **MT-4**

[![](https://ampli-images.s3.amazonaws.com/production/d674515e-e3e9-4cff-8b79-33724a9393f5/original)](https://ampli-images.s3.amazonaws.com/production/d674515e-e3e9-4cff-8b79-33724a9393f5/original)

A classe **mt-4** foi utilizada no lugar da classe **linh**a. O padrão de classes de espaçamento _Bootstrap_ é formado por um caractere representando o tipo de espaçamento (m para _margin_ e p para _padding_), a posição (t para _top_, b para _bottom_, l para _left_ e r para _right_) e um valor numérico, que pode ser substituído por números de 0 a 5 (quanto maior o número, maior o espaçamento da margem).

______

**💭 Reflita**

Observe que o _Bootstrap_ utiliza um padrão lógico para nomear suas classes. Por exemplo: a classe mt-4 aplica uma propriedade _margin-top_; se desejássemos utilizar uma classe para alterar o espaçamento da margem esquerda (_margin-lef_t), poderíamos utilizar a classe **ml-4**.

Com base nisso, reflita sobre possíveis variações de classes _Bootstrap_ para margem e preenchimento e indique a classe do _Bootstrap_ que aumenta ao máximo o preenchimento da margem interna inferior.

______

### **Form-control**

_Form-control_ é a classe que formata entradas de formulários no padrão _Bootstrap_. Ela deve ser aplicada a todos os elementos de um formulário em que se deseja inserir um novo estilo. A figura “Comparação entre o container criado manualmente e o container nativo do Bootstrap” ilustra a diferença entre o estilo criado anteriormente e o estilo padrão do _Bootstrap_.

### **BTN**

A classe btn é responsável por aplicar estilos de formatação em botões. No exemplo, ela recebe o auxílio de duas outras classes: _btn-success_ (aplica o estilo em verde) e _btn-block_ (define a largura do botão em 100%). Há oito variações de cores, além do botão tipo _link_:

[![](https://ampli-images.s3.amazonaws.com/production/5f2e0627-a9bf-4e58-baee-a54014e0d066/original)](https://ampli-images.s3.amazonaws.com/production/5f2e0627-a9bf-4e58-baee-a54014e0d066/original)

Cores aplicadas a botões com Bootstrap.Fonte: adaptada de Bootstrap Team (2020).

Observe o código usado para criar os botões acima:

[![](https://ampli-images.s3.amazonaws.com/production/63ce05b4-a61c-4684-a978-d0dc816e8fb5/original)](https://ampli-images.s3.amazonaws.com/production/63ce05b4-a61c-4684-a978-d0dc816e8fb5/original)

# **Sistema de grade (Grid System)**

[![](https://ampli-images.s3.amazonaws.com/production/03d32520-85f4-452e-b752-facabf7e5ed1/original)](https://ampli-images.s3.amazonaws.com/production/03d32520-85f4-452e-b752-facabf7e5ed1/original)

Um recurso valioso do _Bootstrap_ é o chamado sistema de grade (_grid system_). O principal componente do sistema de grade _Bootstrap_ são os containers.

Anteriormente, definimos nossa classe container com uma largura fixa de 960px, logo, nosso container não era responsivo, uma vez que, independentemente da tela utilizada, nosso container teria sempre 960px. O container _Bootstrap_ determina o tamanho da largura com base na resolução da tela usada para visualizá-lo. Por exemplo: se a tela possuir mais do que 1200 px de largura, o _Bootstrap_ determinará que seu container tenha 1140px, e se for maior do que 992px, então, o máximo será de 960px. Se for maior que 768, o tamanho máximo será de 720px; se for maior que 576px, terá 540px; e se for menor do que isso, o container ocupará 100% do espaço disponível. A ideia do container _Bootstrap_ é impedir que elementos saiam do espaço disponível em tela.

[![](https://ampli-images.s3.amazonaws.com/production/75c5a626-7ec8-400b-8083-28150145f9fc/original)](https://ampli-images.s3.amazonaws.com/production/75c5a626-7ec8-400b-8083-28150145f9fc/original)

Dispositivos e resoluções do sistema de grade Bootstrap. Fonte: elaborado pelo autor.

Após apresentarmos a classe Container, vamos apresentar a classe **container-**_**fluid**__._ Enquanto a classe container respeita os tamanhos disponíveis, a classe **container-**_**fluid**_ utiliza todo o espaço disponibilizado pela tela usada, ou seja, sempre 100% do espaço (com exceção das margens). Isso pode ser interessante, por exemplo, em páginas que exibem tabelas, assim, o máximo de espaço será aproveitado. Entretanto, é preciso atentar-se a monitores muito grandes (como resoluções Full HD: 1920x1080 px ou 4K). Mesmo que a resolução seja muito grande, o _Bootstrap_ tentará utilizar todo o espaço disponível, o que poderá gerar muitos espaços em branco.

Outro ponto importante das classes do _grid system Bootstrap_ são as linhas, colunas e pontos de colapso. _Bootstrap_ trata do sistema de grades como se fosse uma tabela com exatamente 12 colunas. Entretanto, você não precisa usar as 12 colunas, podendo aplicar tamanhos personalizados (desde que sejam múltiplos de 12). Observe a figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/6655897c-4a4f-4d3d-8b39-94e1a2ffbb38/original)](https://ampli-images.s3.amazonaws.com/production/6655897c-4a4f-4d3d-8b39-94e1a2ffbb38/original)

Sistema de grade Bootstrap. Fonte: adaptada de Bootstrap Team (2020).

(A) Exemplos de uso de colunas no _Bootstrap_. A soma dos valores de classes em uma linha deve ser 12 (no máximo). (B) Caso a soma ultrapasse 12, a linha entra em colapso. Nesse exemplo, a última coluna é jogada para a próxima linha, e isso garante a integridade dos elementos da coluna.

A figura abaixo apresenta uma implementação de um simples layout responsivo usando as classes _Bootstrap_.

[![](https://ampli-images.s3.amazonaws.com/production/8a67d186-609b-4ae1-8e28-3040219c49cd/original)](https://ampli-images.s3.amazonaws.com/production/8a67d186-609b-4ae1-8e28-3040219c49cd/original)

[![](https://ampli-images.s3.amazonaws.com/production/9e433263-d108-411f-92f6-26152129ab83/original)](https://ampli-images.s3.amazonaws.com/production/9e433263-d108-411f-92f6-26152129ab83/original)

Implementação de um layout responsivo com classes em Bootstrap. Fonte: elaborado pelo autor.

O código apresentado resultará na página a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/4fc9dfc7-288f-474b-8aba-3b82f0e3df82/original)](https://ampli-images.s3.amazonaws.com/production/4fc9dfc7-288f-474b-8aba-3b82f0e3df82/original)

Linhas (row) e colunas (col) no Bootstrap.Fonte: elaborada pelo autor.

Veja que o padrão de cores apresentado para os botões vale para componentes de pano de fundo (bg-*: sendo bg-_primary_ azul, bg-info verde-água, bg-_warning_ amarelo e bg-_danger_ vermelho). Note, também, que usamos a classe p-5, que é equivalente a pt-5, pr-5, pb-5 e pl-5 usadas ao mesmo tempo. Além disso, aplicamos _text-center_, que centraliza o texto do rodapé.

Podemos, ainda, adicionar um ponto de colapso. Caso a resolução da tela seja pequena, é desejável que a coluna principal e o menu lateral não sejam exibidos lado a lado e sim um abaixo do outro, para isso, basta alterar as classes usadas:

[![](https://ampli-images.s3.amazonaws.com/production/f5557ec7-fd22-41c2-b5d4-dc7748a6b2f8/original)](https://ampli-images.s3.amazonaws.com/production/f5557ec7-fd22-41c2-b5d4-dc7748a6b2f8/original)

Nesse caso, aplicamos duas classes distintas para cada um: col-12 e col-lg-8 para o conteúdo principal e col-12 e col-lg-4 para o menu lateral. Se a tela tiver uma resolução grande, serão aplicadas col-8 e col-4, e se a tela tiver uma resolução pequena, o sistema deverá adotar a classe col-12, i.e., ocupando todo o espaço disponível.

Logo, o mesmo documento exibido na figura”Linhas _(row_) e colunas (_col_) no _Bootstrap_”, em um smartphone, seria visto como ilustrado na figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/02cd28c5-0599-4488-9275-58df78b7244c/original)](https://ampli-images.s3.amazonaws.com/production/02cd28c5-0599-4488-9275-58df78b7244c/original)

Design responsivo do Bootstrap - visualização de um smartphone. Fonte: elaborada pelo autor.

# **Animação e transição utilizando CSS**

[![](https://ampli-images.s3.amazonaws.com/production/4f7b5131-26b7-4555-b04b-8064abed2967/original)](https://ampli-images.s3.amazonaws.com/production/4f7b5131-26b7-4555-b04b-8064abed2967/original)

O CSS3 permite, ainda, a inserção de animações em elementos HTML. As animações do CSS não são tão avançadas quanto aquelas construídas usando-se _JavaScript_, entretanto, elas permitem configurar transições entre estilos CSS. A propriedade responsável por isso é **animation**. Essa classe pode receber, ainda, outras subpropriedades:

[![](https://ampli-images.s3.amazonaws.com/production/777b9f5a-ab51-47d8-a2dd-1460e0335f51/original)](https://ampli-images.s3.amazonaws.com/production/777b9f5a-ab51-47d8-a2dd-1460e0335f51/original)

Subpropriedades de animation.Fonte: elaborada pelo autor.

Vamos adicionar o seguinte efeito no arquivo “estilo.css” e configurar o exemplo anterior:

[![](https://ampli-images.s3.amazonaws.com/production/7ab0caa3-1166-43a8-a0d5-f62e129ff9f6/original)](https://ampli-images.s3.amazonaws.com/production/7ab0caa3-1166-43a8-a0d5-f62e129ff9f6/original)

estilo.css. Fonte: elaborada pelo autor.

Na figura “estilo.css” foi configurada uma animação com duração de 1 segundo denominada surgir_da_direita. Como o próprio nome define, a animação permite que divs surjam na tela pelo lado direito e deslizem até o lado esquerdo. O estilo inicial é definido dentro do bloco iniciado com _**from**_ (observe que a margem esquerda inicial é 100%, ou seja, está fora da vista) e o estilo final é definido no bloco _**to**_ (aqui, a margem esquerda é de 0%). Além disso, foi aplicada uma mudança de tamanho de 300 para 100%, o que gera um efeito redutivo interessante.

[![](https://ampli-images.s3.amazonaws.com/production/886b660b-e9fe-45cb-bcb8-fd4b2ed8cc73/original)](https://ampli-images.s3.amazonaws.com/production/886b660b-e9fe-45cb-bcb8-fd4b2ed8cc73/original)

[![](https://ampli-images.s3.amazonaws.com/production/11a0563b-b8eb-4d5c-bc2f-90453fc4662e/original)](https://ampli-images.s3.amazonaws.com/production/11a0563b-b8eb-4d5c-bc2f-90453fc4662e/original)

[![](https://ampli-images.s3.amazonaws.com/production/acbe2b58-4fd4-46c2-9594-e209dadb2f60/original)](https://ampli-images.s3.amazonaws.com/production/acbe2b58-4fd4-46c2-9594-e209dadb2f60/original)

[![](https://ampli-images.s3.amazonaws.com/production/bfe66992-c65b-4e2a-9016-cdc7aa118afd/original)](https://ampli-images.s3.amazonaws.com/production/bfe66992-c65b-4e2a-9016-cdc7aa118afd/original)

Exemplo de animação em quatro períodos distintos. Fonte: elaborada pelo autor.

Aqui, apresentamos fundamentos da aplicação de estilos para tabelas e formulários; conhecemos os _frameworks Bootstrap_ e _DataTables;_ por fim, vimos como realizar animações básicas usando CSS. Agora, é o momento de demonstrar na prática o conhecimento adquirido. Vamos lá?

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)

_DataTables_ é uma biblioteca especialmente construída para formatação de tabelas, ele contém funcionalidades avançadas que podem ser inseridas com poucas linhas de código.

A seguir, você poderá entender como cada parte foi construída:

**Tecnologias usadas:**

- _Bootstrap 4.5._
- _DataTables._
- Imagens coletadas no _Pixabay_.

Estrutura em que o código foi organizado, conforme a figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/3c0447e9-0808-4cff-bfa4-88cd3ed8130d/original)](https://ampli-images.s3.amazonaws.com/production/3c0447e9-0808-4cff-bfa4-88cd3ed8130d/original)

Estrutura de diretórios e organização da página. Fonte: elaborada pelo autor.

O documento web está disponível em _index_.html; optamos por construir apenas um arquivo HTML para todo o conteúdo; o arquivo CSS principal foi incluído em dados/css/; foi utilizada a CDN para o _DataTables_ e _Bootstrap_; e as Imagens foram inseridas em dados/img e obtidas no _Pixabay_.

A maior parte dos códigos de estilo utilizou o _Bootstrap_ e poucas alterações foram realizadas na folha de estilo principal. Observe a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/0280d6e8-c75b-4498-81b3-8919e6b7cf62/original)](https://ampli-images.s3.amazonaws.com/production/0280d6e8-c75b-4498-81b3-8919e6b7cf62/original)

[![](https://ampli-images.s3.amazonaws.com/production/f13c6ad5-55d1-485b-9d30-29d9ef146ecf/original)](https://ampli-images.s3.amazonaws.com/production/f13c6ad5-55d1-485b-9d30-29d9ef146ecf/original)

estilo.css. Fonte: elaborada pelo autor.

Aqui, destacamos a classe “sobreposicao", que insere um fundo com 70% de transparência sobre a div “quem-somos”. Esta, por sua vez, exibe uma imagem de fundo, logo, preste a atenção na forma como o link da imagem de fundo foi declarado:

[![](https://ampli-images.s3.amazonaws.com/production/5216dacd-c13b-45eb-85e3-e270ab105189/original)](https://ampli-images.s3.amazonaws.com/production/5216dacd-c13b-45eb-85e3-e270ab105189/original)

O CSS procurará a imagem com base na sua localização atual. Lembre-se de que o arquivo está disponível em dados/css/estilo.css, logo, para encontrar a imagem de fundo, ele deverá partir dessa posição. A imagem se encontra em dados/img/ computer-768608_1280.jpg, entretanto, a pasta “dados” foi substituída por “..”. O símbolo “..” indica o diretório anterior, então, a imagem se encontra dentro da pasta “img”, que está um diretório atrás.

**Página inicial**

Todas as páginas foram incluídas dentro de “index.html” e podem ser acessadas por _links_ internos \#nome-do-id. Para um melhor entendimento do código, dividimos ele em seis partes:

Na primeira parte, fizemos as declarações de _tags_ iniciais e incluímos três folhas de estilo: (i) folha de estilo do _DataTables_ (pela CDN), (ii) folha de estilos do _Bootstrap_ (pela CDN) e (iii) folha de estilo principal (apresentada anteriormente).

Em seguida, fizemos a abertura das _tags_ <_body_> e <_header_> e inserimos o cabeçalho. Optamos por utilizar o menu nativo do _Bootstrap_.

Depois, construímos duas colunas de tamanhos _col-lg-5_ e _col-lg-7_ para receber uma imagem e um texto de descrição. Preste a atenção nas classes _Bootstrap_ utilizadas para inserir detalhes nos estilos dos elementos exibidos. Confira a figura a seguir com a primeira parte da implementação index.html.

[![](https://ampli-images.s3.amazonaws.com/production/e4c8af8d-1eaf-48a7-b1a0-10f3bf86433c/original)](https://ampli-images.s3.amazonaws.com/production/e4c8af8d-1eaf-48a7-b1a0-10f3bf86433c/original)

[![](https://ampli-images.s3.amazonaws.com/production/986ba471-2e11-41d4-827d-7b8513465ab6/original)](https://ampli-images.s3.amazonaws.com/production/986ba471-2e11-41d4-827d-7b8513465ab6/original)

[![](https://ampli-images.s3.amazonaws.com/production/0bf9ab03-6900-4cf4-b917-dba5ffdcfc48/original)](https://ampli-images.s3.amazonaws.com/production/0bf9ab03-6900-4cf4-b917-dba5ffdcfc48/original)

[![](https://ampli-images.s3.amazonaws.com/production/f989b52d-93a1-4bfb-bd3e-e7178086dad5/original)](https://ampli-images.s3.amazonaws.com/production/f989b52d-93a1-4bfb-bd3e-e7178086dad5/original)

[![](https://ampli-images.s3.amazonaws.com/production/a8bf7ac7-f8ef-4cc0-82de-d4f14f2799ed/original)](https://ampli-images.s3.amazonaws.com/production/a8bf7ac7-f8ef-4cc0-82de-d4f14f2799ed/original)

[![](https://ampli-images.s3.amazonaws.com/production/6b9643ab-ecee-4b53-a4b0-36a8273c84ec/original)](https://ampli-images.s3.amazonaws.com/production/6b9643ab-ecee-4b53-a4b0-36a8273c84ec/original)

index.html (parte 1). Fonte: elaborada pelo autor.

Essa primeira parte do código produzirá a página ilustrada a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/72538104-4f0c-4c7e-a461-c941976e44d3/original)](https://ampli-images.s3.amazonaws.com/production/72538104-4f0c-4c7e-a461-c941976e44d3/original)

Página construída. Fonte: elaborada pelo autor.

Uma das vantagens de se utilizar o menu do _Bootstrap_ é que ele se adapta ao dispositivo utilizado (design responsivo). A figura a seguir ilustra o resultado da página no smartphone.

[![](https://ampli-images.s3.amazonaws.com/production/23bcb19a-14fb-4a2d-ba72-0aa849639bc5/original)](https://ampli-images.s3.amazonaws.com/production/23bcb19a-14fb-4a2d-ba72-0aa849639bc5/original)

Visão da página em um smartphone. Fonte: elaborada pelo autor.

Perceba que, nesse exemplo, a imagem foi enviada para a parte superior e o texto para a parte inferior (isso se deve às classes _Bootstrap_ utilizadas). A esse processo de adaptação dá-se o nome de design responsivo.

**Seção Quem Somos**

Em seguida, destacamos uma seção para exibir uma mensagem que apresente a empresa. Chamamos essa seção de “quem-somos”. Nela, adicionamos uma imagem de fundo e uma segunda camada posterior na cor preta, mas com 70% de transparência. A transparência foi definida no arquivo estilo.css, na linha:

background-color: rgba('0, 0, 0, 0.7');

**rgba**: indica a quantidade de vermelho (r), verde (g) e azul (b). O último valor (a), conhecido como alpha, indica o índice de transparência, que vai de 0 a 1 (no exemplo, 0.7 indica 70% de transparência).

[![](https://ampli-images.s3.amazonaws.com/production/b51ff3ff-fee5-4b68-abff-5615fe872863/original)](https://ampli-images.s3.amazonaws.com/production/b51ff3ff-fee5-4b68-abff-5615fe872863/original)

index.html (parte 2) – Quem somos. background-color: rgba('0, 0, 0, 0.7');

A figura a seguir ilustra como a página ficará ao ser exibida:

[![](https://ampli-images.s3.amazonaws.com/production/09244fdd-cc06-45dc-890b-9a0632b94f60/original)](https://ampli-images.s3.amazonaws.com/production/09244fdd-cc06-45dc-890b-9a0632b94f60/original)

Visão da página. Fonte: elaborada pelo autor.

**Painel de planos**

Construímos uma seção para exibir uma lista de planos disponíveis. Para essa seção, optamos por utilizar a classe cards do _Bootstrap_.

Observe a implementação no painel de planos a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/13198bc2-bf1a-4875-8f1c-1c3305c52b42/original)](https://ampli-images.s3.amazonaws.com/production/13198bc2-bf1a-4875-8f1c-1c3305c52b42/original)

[![](https://ampli-images.s3.amazonaws.com/production/5a1120bf-718d-4923-a457-dc54d3d24bc9/original)](https://ampli-images.s3.amazonaws.com/production/5a1120bf-718d-4923-a457-dc54d3d24bc9/original)

[![](https://ampli-images.s3.amazonaws.com/production/56c170e0-5c6b-4e0e-85bc-d906dadf757b/original)](https://ampli-images.s3.amazonaws.com/production/56c170e0-5c6b-4e0e-85bc-d906dadf757b/original)

[![](https://ampli-images.s3.amazonaws.com/production/935ac8b7-6878-49df-8445-b5cc5b208401/original)](https://ampli-images.s3.amazonaws.com/production/935ac8b7-6878-49df-8445-b5cc5b208401/original)

index.html (parte 3) – Painel de Planos. Fonte: elaborada pelo autor.

Veja como essa página ficará ao ser exibida:

[![](https://ampli-images.s3.amazonaws.com/production/35a0bd04-d7ca-4f15-a8f1-b734738057ba/original)](https://ampli-images.s3.amazonaws.com/production/35a0bd04-d7ca-4f15-a8f1-b734738057ba/original)

Visualização da página Planos criada. Fonte: elaborada pelo autor.

Aqui, dividimos uma linha em quatro colunas (col-md-3). Em cada card, exibimos os preços, o título do plano e um botão “assine já”; além disso, inserimos o quinto plano em um card logo abaixo, e fizemos isso para dar destaque a ele.

**Tabela comparativa**

Em seguida, construímos uma tabela comparativa para os planos. Nesse caso, combinamos o _DataTables_ com as classes destinadas à formatação de tabelas do _Bootstrap_. Veja:

[![](https://ampli-images.s3.amazonaws.com/production/6191e0fa-8261-4b6e-8b17-718440833bde/original)](https://ampli-images.s3.amazonaws.com/production/6191e0fa-8261-4b6e-8b17-718440833bde/original)

[![](https://ampli-images.s3.amazonaws.com/production/4a91d6a3-3a96-4a98-b8a5-91494a9bd074/original)](https://ampli-images.s3.amazonaws.com/production/4a91d6a3-3a96-4a98-b8a5-91494a9bd074/original)

[![](https://ampli-images.s3.amazonaws.com/production/02b5ec1a-62f5-4034-9265-bce200f09811/original)](https://ampli-images.s3.amazonaws.com/production/02b5ec1a-62f5-4034-9265-bce200f09811/original)

[![](https://ampli-images.s3.amazonaws.com/production/c9182423-adbb-4544-848e-24f98c7c4dad/original)](https://ampli-images.s3.amazonaws.com/production/c9182423-adbb-4544-848e-24f98c7c4dad/original)

[![](https://ampli-images.s3.amazonaws.com/production/06470d37-03f1-4e39-877c-30f008be95d4/original)](https://ampli-images.s3.amazonaws.com/production/06470d37-03f1-4e39-877c-30f008be95d4/original)

index.html (parte 4) – Tabela comparativa para planos. Fonte: elaborada pelo autor.

A figura abaixo ilustra a página com a tabela comparativa de planos.

[![](https://ampli-images.s3.amazonaws.com/production/25dc4776-d364-46ae-ad50-eba02ae590f4/original)](https://ampli-images.s3.amazonaws.com/production/25dc4776-d364-46ae-ad50-eba02ae590f4/original)

Tabela comparativa de planos. Fonte: elaborada pelo autor.

Aqui, destacamos a classe _table-responsive-sm_ inserida na tabela. Essa classe é necessária para tornar tabelas responsivas. Se a tabela ultrapassar o limite estabelecido pelo container, o _Bootstrap_ inserirá uma barra horizontal que permite a navegação pela tabela sem colapsar a página. É importante ressaltarmos que as configurações no estilo do _DataTables_ para essa tabela foram realizadas na _tag_ <_footer_>.

**Seção fale conosco**

A seção fale conosco foi desenvolvida com base nos scripts construídos anteriormente. Observe a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/20092eca-620e-43c4-8a3a-b13660658703/original)](https://ampli-images.s3.amazonaws.com/production/20092eca-620e-43c4-8a3a-b13660658703/original)

[![](https://ampli-images.s3.amazonaws.com/production/ccbe8470-acd7-4250-bc25-94be72729d0b/original)](https://ampli-images.s3.amazonaws.com/production/ccbe8470-acd7-4250-bc25-94be72729d0b/original)

[![](https://ampli-images.s3.amazonaws.com/production/47fa3afd-cc51-413f-ac77-a9a6a1c87ac0/original)](https://ampli-images.s3.amazonaws.com/production/47fa3afd-cc51-413f-ac77-a9a6a1c87ac0/original)

Página da seção Fale conosco. Fonte: elaborada pelo autor.

**Rodapé**

Por fim, adicionamos o rodapé na página. Aqui, adicionamos apenas uma mensagem indicando a fonte das imagens utilizadas, que foram coletadas do _Pixabay_ gratuitamente, e embora a atribuição de fonte não seja obrigatória pelos termos do _Pixabay_, é uma boa prática informar a fonte de onde as imagens foram obtidas. Além disso, adicionamos, também, alguns _scripts_: jQuery, _Bootstrap Bundle_ e _DataTables_. Esses scripts são requisitados pelos _frameworks_ utilizados.

Além disso, incluímos um _script_ que altera os padrões de exibição da tabela. Esse _script_ remove a paginação, a barra de informações e de buscas. Observe a seguir a criação do rodapé. Veja que incluímos uma imagem com o _link_ do _Pixabay_.

[![](https://ampli-images.s3.amazonaws.com/production/ad201768-bf15-41b6-b327-1c51f086551b/original)](https://ampli-images.s3.amazonaws.com/production/ad201768-bf15-41b6-b327-1c51f086551b/original)

[![](https://ampli-images.s3.amazonaws.com/production/59f37758-738d-4a7a-8912-6999411d7107/original)](https://ampli-images.s3.amazonaws.com/production/59f37758-738d-4a7a-8912-6999411d7107/original)

index.html (parte 6) – Rodapé. Fonte: elaborada pelo autor.

  

  

# **Referências**

[![](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)

BOOTSTRAP TEAM. **Bootstrap**. [s.d.]. Disponível em: <https://getbootstrap.com/>. Acesso em: 31 jul. 2021.CHIEF OF

DESIGN. **Curso de HTML e CSS - Float Left, Right [Aula 25].** [S.l.: s.n.], 2019. 1 vídeo (5:20 min.) Publicado pelo canal Chief of Design. Disponível em: <https://bit.ly/3edv64Q>. Acesso em: 31 jul. 2021.

CHIEF OF DESIGN. **Curso de HTML e CSS - Z-index [Aula 24]**. [S.l.: s.n.], 2019. 1 vídeo (6:09 min.) Publicado pelo canal Chief of Design. Disponível em: <https://bit.ly/30g9MDL>. Acesso em: 31 jul. 2021.

COYIER, C. **A complete guide to the table element.** 2013. Disponível em: <https://bit.ly/3sTGvuK>. Acesso em: 31 jul. 2021.

**Fundamentos das CSS**. [S.l.: s.n.], 2017. 1 vídeo (12:24 min.) Pulbicado pelo canal Diego Mariano. Disponível em: <https://bit.ly/3c6pbff>. Acesso em: 31 jul. 2021.

MARIANO, D. **CSS3.** [S.l.: s.n.], 2017. 1 vídeo (8:02 min.) Publicado pelo canal Diego Mariano. Disponível em: <https://bit.ly/2MOrCuo>. Acesso em: 31 jul. 2021.

MARIANO, D. **Estrutura de páginas. Diegomariano**. 15 ago. 2020. Disponível em: <https://bit.ly/3qieivV>. Acesso em: 31 jul. 2021.

MARIANO, D. **Folhas de estilo em cascata (CSS)**. Diegomariano. 15 ago. 2020a. Disponível em: <https://bit.ly/3c4oNxR:. Acesso em: 31 jul. 2021.

MARIANO, D. **Iniciando a construção de um Website**. Diegomariano. 15 ago. 2020b. Disponível em: <https://bit.ly/3kQ2NuL>. Acesso em: 31 jul. 2021.

MARIANO, D.; DE MELO-MINARDI, R. **Introdução à programação web para bioinformática: html, css, php and javascript.** [S.l.]: Independently Published, 2017.

MARIANO, D.; DE MELO-MINARDI, R. **Introdução à programação web para bioinformática: html, css, php and javascript.** [S.l.]: Independently Published, 2017.

MAUJOR. **As 8 propriedade css para estilização de fontes e seus segredos.** 2016. Disponível em: <https://bit.ly/3rgXdUt>. Acesso em: 31 jul. 2021.

MAUJOR. **CSS moderno explicado para dinossauros**. 2016. Disponível em: <https://bit.ly/3sQkNrO>. Acesso em: 31 jul. 2021.

MAUJOR. **Tabelas de dados acessíveis**. 2011. Disponível em: <https://bit.ly/3qeRRrC>. Acesso em: 31 jul. 2021.

MDN WEB DOCS. **CSS básico**. 2020. Disponível em: <https://mzl.la/38a6juQ>. Acesso em: 31 jul. 2021.

MDN WEB DOCS. **Float. 2019**. Disponível em: <https://mzl.la/3sVaF0C>. Acesso em: 31 jul. 2021.

MDN WEB DOCS. **Referência de CSS.** 2020. Disponível em: <https://mzl.la/3sJcZrA>. Acesso em: 31 jul. 2021.

MDN WEB DOCS. **Tabelas**. 2019. Disponível em: <https://mzl.la/3kNVFPu>. Acesso em: 31 jul. 2021.

SILVA, M. S. **Fundamentos de HTML5 e CSS3.** São Paulo: Novatec Editora, 2018.

SILVEIRA, D. **Brasil tem mais de 207 milhões de habitantes, segundo IBGE**. 2017. Disponível em: <https://glo.bo/3bjRUyd>. Acesso em: 31 jul. 2021.

W3SCHOOLS. **CSS Box Model**. [s.d.]. Disponível em: <https://bit.ly/3cjcvlF>. Acesso em: 31 jul. 2021.

W3SCHOOLS. **CSS font property**. 2021. Disponível em: <https://bit.ly/3eb1uW2>. Acesso em: 31 jul. 2021.