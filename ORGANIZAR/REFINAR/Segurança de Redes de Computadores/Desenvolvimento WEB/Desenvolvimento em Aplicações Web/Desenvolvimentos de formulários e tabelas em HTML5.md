# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/8cad07b5-6f4e-4443-ae69-ad240b21487b/original)](https://ampli-images.s3.amazonaws.com/production/8cad07b5-6f4e-4443-ae69-ad240b21487b/original)

### **Qual é o foco da aula?**

Nesta aula, você verá a construção de tabelas e formulários em HTML.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- apontar formulários HTML interativos;
- descrever a linguagem _back-end_;
- examinar outras _tags_ relacionadas a tabelas.

**Situação-problema**

Olá! Nesta aula, você aprenderá sobre a construção de tabelas (componentes que permitem a inserção de dados tabulares) e de formulários (tipos de elementos HTML usados para envio de informações).

Tabelas são essenciais para organizar dados e podem ser criadas usando-se a _tag_ <table>. Devemos ressaltar que cada elemento da tabela deve ser declarado separadamente usando-se a _tag_ <td>, que representa uma célula. Além disso, um conjunto de células deve ser organizado em uma linha, que deve ser criada usando-se o comando <tr>. Apesar de as tabelas poderem receber uma quantidade maior de linhas, essas são consideradas as principais _tags_ para se produzir uma tabela mínima. Nesta aula, você conhecerá também as outras _tags_ relacionadas a tabelas e suas particularidades.

Por fim, você também verá como criar formulários HTML, que permitem que clientes interajam com seu website. A função dos formulários é receber valores digitados ou arquivos inseridos e, então, enviá-los para o servidor, por meio de uma página previamente estabelecida, a fim de que seja processado por uma linguagem _back-end_.

Formulários possuem uma variada gama de entradas de diversos tipos, facilitando a compreensão dos clientes sobre o que deve ser enviado e auxiliando o desenvolvedor na coleta de diferentes tipos de dados, sem que haja problemas em seu formato.

Vide por exemplo um sistema que coleta data de nascimento. Qual seria a forma ideal de digitar a data? 01-01-2021, 01/01/2021 ou 1º de janeiro de 2021? E para clientes de países em que o mês é digitado em uma posição invertida ao dia? Todas essas questões representam problemas na hora de processar os dados. Por isso, HTML5 apresentou a _tag_ input do tipo date, que coleta a data correta, pedindo ao usuário que apenas a selecione no calendário.

Para colocar em prática os conhecimentos a serem aprendidos nesta aula, considere que você foi contratado por uma empresa que possui sistema de atendimento telefônico e atendimento por e-mail. Entretanto, poucas pessoas utilizam o serviço de e-mail para contatá-los. Vendo a necessidade de facilitar essa dinâmica, a equipe definiu que deve ser construída uma página de contato dentro do site da empresa. Essa página deverá receber o nome, o e-mail, o telefone de contato, o assunto e a mensagem do cliente. Todas essas informações deverão, então, ser enviadas para a caixa de mensagens da empresa.

Diante disso, requisitaram a você para construir essa página por meio da qual os clientes da empresa de planos de internet poderão entrar em contato com o estabelecimento. Você, então, pesquisou modelos de formulários de contato e encontrou o exemplo da figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/17e60ccc-48de-41a2-a6ff-81494479150b/original)](https://ampli-images.s3.amazonaws.com/production/17e60ccc-48de-41a2-a6ff-81494479150b/original)

Exemplo de formulário de contato. Fonte: Captura de tela do menu contato da Biblioteca Virtual da Kroton elaborada pelo autor.

Com base no modelo apresentado na figura acima, construa um código HTML que reproduza um formulário de contato. Utilize tabelas sem bordas para alinhar os campos **e-mail** e **telefone**.

Neste momento, não se preocupe com o processamento e o envio de e-mails, pois isso será apresentado posteriormente. E quando tratarmos sobre CSS, aprenderemos métodos melhores para alinhar elementos lado a lado.

Vamos, então, aprender a construir tabelas e formulários?

Bons estudos!

# **Tabelas**

[![](https://ampli-images.s3.amazonaws.com/production/9bb21cc7-b710-402f-9363-fc4a414b2c4d/original)](https://ampli-images.s3.amazonaws.com/production/9bb21cc7-b710-402f-9363-fc4a414b2c4d/original)

Estudante, você já viu como páginas podem ser estruturadas, agora, verá _tags_ que representam componentes importantes do HTML, como as tabelas.

Você já deve ter visto alguma tabela, no entanto, é importante que relembre alguns conceitos para entender como ela é interpretada em HTML. Uma tabela possibilita organizar informações em três componentes principais: colunas, linhas e células, conforme a figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/7a47dee1-e4cd-4318-9817-d62b64938fdf/original)](https://ampli-images.s3.amazonaws.com/production/7a47dee1-e4cd-4318-9817-d62b64938fdf/original)

Exemplo de tabela. Fonte: Elaborado pelo autor.

Nas primeiras versões do HTML, as tabelas eram utilizadas como um elemento estrutural, para se organizar o layout da tela. Nas versões mais recentes, novas _tags_ estruturais foram introduzidas e tabelas passaram a ser utilizadas apenas para exibir dados tabulares (TITTEL; NOBLE; COUTO, 2018).

Em HTML, tabelas são definidas por meio da tag composta <table>. Ao criar uma tabela, as linhas são inseridas por meio da _tag_ <tr>. Células podem ser inseridas usando-se a _tag_ <th>, para célula de cabeçalho, ou <td>, para células comuns. Por padrão, o texto inserido a partir da _tag_ de cabeçalho <th> está em negrito, enquanto os elementos inseridos por meio da _tag_ de células comuns <td> são alinhados à esquerda em fonte normal. A figura abaixo ilustra como uma tabela pode ser estruturada em HTML.

[![](https://ampli-images.s3.amazonaws.com/production/57abbb6b-0239-4f6a-a1cd-7ad6297c7349/original)](https://ampli-images.s3.amazonaws.com/production/57abbb6b-0239-4f6a-a1cd-7ad6297c7349/original)

Exemplo básico de tabela. Fonte: Mariano; de Melo-Minardi (2017, p. 75).

A figura a seguir nos mostra um exemplo de uma simples tabela em HTML. A saída do código da tabela pode ser visualizada na figura abaixo (Visualização da tabela no navegador) e corresponde à visualização em um navegador (browser). No simulador, você consegue executar e modificar a informação da tabela.

[![](https://ampli-images.s3.amazonaws.com/production/525c3076-f2f5-4831-bec6-abcc9e1cac65/original)](https://ampli-images.s3.amazonaws.com/production/525c3076-f2f5-4831-bec6-abcc9e1cac65/original)

[![](https://ampli-images.s3.amazonaws.com/production/decfe5e3-52f5-4fbc-8873-21beed64f2ca/original)](https://ampli-images.s3.amazonaws.com/production/decfe5e3-52f5-4fbc-8873-21beed64f2ca/original)

Exemplo de uma tabela em HTML. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/c10ef92b-f365-451f-9964-4cfc702c251d/original)](https://ampli-images.s3.amazonaws.com/production/c10ef92b-f365-451f-9964-4cfc702c251d/original)

Visualização da tabela no navegador. Fonte: Captura de tela do index.html elaborada pelo autor.

Vamos interpretar cada parte do código:

[![](https://ampli-images.s3.amazonaws.com/production/e1343b0b-86f5-40cd-941a-4c1618bfb5d8/original)](https://ampli-images.s3.amazonaws.com/production/e1343b0b-86f5-40cd-941a-4c1618bfb5d8/original)

[![](https://ampli-images.s3.amazonaws.com/production/b2081f2b-420e-4f49-b737-a7ba85bc0943/original)](https://ampli-images.s3.amazonaws.com/production/b2081f2b-420e-4f49-b737-a7ba85bc0943/original)

Por padrão, tabelas inseridas não possuem borda. Você pode inseri-las usando o atributo border, que recebe um valor numérico indicando a largura desejada para a borda, conforme vemos na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/23972e87-dcb6-4c11-a2fd-a2fc28d803db/original)](https://ampli-images.s3.amazonaws.com/production/23972e87-dcb6-4c11-a2fd-a2fc28d803db/original)

Tabela com bordas. Fonte: Captura de tela do index.html elaborada pelo autor.

Você pode, ainda, adicionar cor ao fundo de uma tabela usando o atributo bg_color_, que recebe o nome da cor desejada (em inglês). Neste caso, foi inserida a cor amarela (_yellow_).

Outra forma de se inserir cor é utilizando códigos em hexadecimal da cor. Na figura abaixo (Alterando cor de fundo de uma tabela), podemos observar a cor do fundo da tabela.

[![](https://ampli-images.s3.amazonaws.com/production/c50dbf17-b9f6-4218-bcc2-9e9e1a804d6e/original)](https://ampli-images.s3.amazonaws.com/production/c50dbf17-b9f6-4218-bcc2-9e9e1a804d6e/original)

[![](https://ampli-images.s3.amazonaws.com/production/29112cfa-9cc4-4246-babd-9a573f93901d/original)](https://ampli-images.s3.amazonaws.com/production/29112cfa-9cc4-4246-babd-9a573f93901d/original)

Alterando cor de fundo de uma tabela. Fonte: Captura de tela do index.html elaborada pelo autor.

A seguir, apresentaremos uma tabela em HTML contendo algumas cores e seus códigos em hexadecimal. Observe que utilizamos o atributo bg_color_ com a _tag_ <td> para cada linha da primeira coluna na tabela; já na segunda coluna, temos os códigos em hexadecimal. Tais cores podem ser utilizadas na concepção de uma página web em HTML. Observe a tabela e seu código na ferramenta _Trinket_:

[![](https://ampli-images.s3.amazonaws.com/production/f8e9c3cc-6617-4b42-ad0f-e254e5d9fbc9/original)](https://ampli-images.s3.amazonaws.com/production/f8e9c3cc-6617-4b42-ad0f-e254e5d9fbc9/original)

Pode-se, ainda, alterar a largura e a altura de partes da tabela. No exemplo a seguir, faremos a alteração da altura e da largura apenas da primeira linha, observe o resultado na figura a seguir e o código alterado na ferramenta _Trinket_

[![](https://ampli-images.s3.amazonaws.com/production/3aafbed2-d662-4b54-b235-3fe3d0d7f5d6/original)](https://ampli-images.s3.amazonaws.com/production/3aafbed2-d662-4b54-b235-3fe3d0d7f5d6/original)

Alterando largura e altura de partes de uma tabela. Fonte: Captura de tela do index.html elaborada pelo autor.

O atributo _height_ recebe um valor em _pixels_ para definir a altura do item. Observe que ele foi aplicado apenas na primeira linha <tr>. O atributo _width_ determina a largura do item, logo, observe que, após ter sido aplicado em cada célula, a largura delas nas linhas seguintes também foi alterada.

______

**💭 Reflita**

Apesar desses atributos permitirem alterações de cores, bordas e larguras, a sua utilização não é recomendada. É preferível o uso de propriedades de estilo CSS (que estudaremos em outro momento).

**Quais seriam os motivos para isso?**

# **Mesclando células**

[![](https://ampli-images.s3.amazonaws.com/production/ad37d0dc-ef4a-401e-9567-d886f9b3a553/original)](https://ampli-images.s3.amazonaws.com/production/ad37d0dc-ef4a-401e-9567-d886f9b3a553/original)

É possível **mesclar células** usando o atributo colspan, utilizado para mesclar colunas, como na Figura 1.39. Podemos, ainda, **mesclar linhas** utilizando o atributo _rowspan_. Observe a estrutura na figura a seguir (Atributo rowspan). Esses atributos podem ser utilizados tanto em células do tipo <th> quanto do tipo <td>. Para isso, primeiro você deve determinar quantas colunas serão mescladas (no exemplo a seguir, duas). A seguir, utilizar o atributo colspan para indicar quais células serão unidas. Como mencionado, pode-se, ainda, utilizar a propriedade _rowspan_ para unir linhas.

[![](https://ampli-images.s3.amazonaws.com/production/addc3413-7e20-4d07-bdbb-d79584712482/original)](https://ampli-images.s3.amazonaws.com/production/addc3413-7e20-4d07-bdbb-d79584712482/original)

Atributo colspan. Fonte: Adaptada de Mariano; de Melo-Minardi (2017).

[![](https://ampli-images.s3.amazonaws.com/production/9ae5ce77-d27c-4cbb-814c-60ef4af6b360/original)](https://ampli-images.s3.amazonaws.com/production/9ae5ce77-d27c-4cbb-814c-60ef4af6b360/original)

Atributo rowspan. Fonte: Adaptada de Mariano; de Melo-Minardi (2017).

# **Novidades de HTML5 para tabelas**

[![](https://ampli-images.s3.amazonaws.com/production/b5149fd8-67b6-47ba-8354-830772821e0a/original)](https://ampli-images.s3.amazonaws.com/production/b5149fd8-67b6-47ba-8354-830772821e0a/original)

HTML5 trouxe _tags_ que permitem uma melhor maneira de organizar tabelas: <_thead>, <tbody> e <tfoot_>. A _tag <thead>_ é utilizada para inserir as células do cabeçalho. O conteúdo da tabela deve ser inserido em _<tbody>_; já _<tfoot>_ pode ser usado para inserção de linhas conclusivas ou de notas de rodapé. Observe a tabela criada e ilustrada na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/3c64f940-b393-4a85-92da-1e03aaf6fa0c/original)](https://ampli-images.s3.amazonaws.com/production/3c64f940-b393-4a85-92da-1e03aaf6fa0c/original)

Tags <thead>, <tbody> e <tfoot>. Fonte: Captura de tela do index.html elaborada pelo autor.

Estudante, agora que você conhece as _tags_ para criação de tabela, aprenderá a criar outro elemento em HTML: os formulários. Você já deve ter se deparado com páginas de serviços na internet em que é preciso preencher formulários de contato, de suporte, de atendimento, orçamento, compras, cadastro, entre outros. Então, agora você conhecerá algumas das _tags_ utilizadas na construção de formulários.

# **Formulários**

[![](https://ampli-images.s3.amazonaws.com/production/3c01cb6d-8648-4082-b6ea-e5379bab36ec/original)](https://ampli-images.s3.amazonaws.com/production/3c01cb6d-8648-4082-b6ea-e5379bab36ec/original)

Formulários são tipos de elementos HTML usados para coletar os dados que o desenvolvedor deseja processar e/ou salvar (TITTEL; NOBLE; COUTO, 2018). O uso de formulários é a forma mais efetiva para se obter dados relevantes dos usuários do seu website (GUPTA, 2013). A figura abaixo ilustra um exemplo de formulário de contato com alguns campos para inclusão de dados pessoais e mensagem.

[![](https://ampli-images.s3.amazonaws.com/production/7faeef6f-3c8f-442d-a901-fb0c1ffde1b2/original)](https://ampli-images.s3.amazonaws.com/production/7faeef6f-3c8f-442d-a901-fb0c1ffde1b2/original)

Exemplo de formulário de contato. Fonte: Captura de tela do menu contato da Biblioteca Virtual da Kroton elaborada pelo autor.

Formulários podem ser criados usando-se a _tag_ <_form_>, que pode receber como principais atributos _action, method_ e _name_ (MARIANO; DE MELO-MINARDI, 2017). O atributo _action_ informa ao navegador para qual endereço deve enviar as informações presentes no formulário; o atributo _method_ indica o método a ser utilizado para envio (_POST_ e _GET_ são os mais comuns); por fim, o atributo _name_ indica o nome utilizado para o formulário.

______

🔁 Assimile

_POST versus GET_

No método _POST_, as informações passadas pelo formulário são transmitidas junto ao corpo da requisição HTTP (ou seja, a transmissão é feita de forma criptografada).

_POST_ pode ser utilizado, por exemplo, para envio de arquivos ou em formulários com dados sigilosos.

Por outro lado, os envios por meio do método _GET_ transmitem os dados pela URL da página. Por exemplo:

[www.site.com.br/?id=1](http://www.site.com.br/?id=1)

Nesse exemplo, é feita uma requisição do tipo _GET_, em que a variável **id** é igual a 1. Portanto, os dados enviados em _GET_ são visualmente públicos (MARIANO; DE MELO-MINARDI, 2017).

______

Além de _name, method_ e _action_, formulários podem receber o atributo _enctyp_e. O atributo _enctype_ determina como os dados do formulário devem ser codificados quando enviados ao servidor. Ele pode receber os valores: (i) _application_/x-www-_form-urlencoded_, para caracteres codificados antes do envio; (ii) _multipart/form-dat_a, usado para envio de arquivos, uma vez que não fornece codificação; e (iii) _text/plain_, que codifica apenas os espaçamentos.

[![](https://ampli-images.s3.amazonaws.com/production/b8d30b12-6f5f-4f6b-a367-902174244df4/original)](https://ampli-images.s3.amazonaws.com/production/b8d30b12-6f5f-4f6b-a367-902174244df4/original)

Exemplo de um formulário. Fonte: Elaborado pelo autor.

A seguir, o código é explicado:

- observe que o formulário é aberto por meio da _tag_ <_form>_ e fechado via _tag_ </_form_>.
- em _name_="meu_primeiro_formulario", define-se o nome do formulário. No caso, ele foi nomeado como “meu_primeiro_formulario”. Observe que evitamos o uso de espaços ou outros caracteres especiais. Isso se dá uma vez que esse nome pode ser utilizado na etapa de processamento, já os caracteres especiais podem ser codificados ou não, a depender do tipo de _enctype_ utilizado para envio.
- em _method="POST"_ define-se o método de envio considerado, o qual foi o _POST_.
- em _action_="gravaDados.php" define-se que o atributo _action_ aponta para “gravarDados.php”. Assim, para que esse formulário funcione corretamente, deve existir um arquivo denominado “gravarDados.php”, que recebe os dados enviados pelo método _POST_ e processa-os usando a linguagem de programação PHP (outras linguagens também podem ser utilizadas, entretanto, citaremos apenas PHP aqui, pois será a linguagem abordada ao final dos nossos estudos).
- por fim, em _enctype="multipart/form-data"_, define-se que o _enctype_ utilizado é o “_multipart/form-data_”. Declarar o _enctype_ é necessário quando queremos enviar arquivos anexados ao formulário.

A seguir, você conhecerá os elementos que podem ser incluídos em formulários HTML.

# **Elementos de formulários**

[![](https://ampli-images.s3.amazonaws.com/production/fc2ee8c2-0fa5-4b3a-b0ad-92c4c0801e6e/original)](https://ampli-images.s3.amazonaws.com/production/fc2ee8c2-0fa5-4b3a-b0ad-92c4c0801e6e/original)

Há uma série de elementos que tornam os formulários HTML altamente versáteis:

- menu de seleção: elemento que fornece um menu suspenso que será exibido quando o usuário clicar. É criado com a _tag_ <_select_>. Cada item é adicionado usando-se a _tag_ <_option_>. Observe o exemplo com um menu de seleção com os dias da semana.

[![](https://ampli-images.s3.amazonaws.com/production/aaa212e7-7d0a-4744-90af-735f7426ca03/original)](https://ampli-images.s3.amazonaws.com/production/aaa212e7-7d0a-4744-90af-735f7426ca03/original)

Menu de seleção com os dias da semana. Fonte: Elaborado pelo autor.

No exemplo, observe que a _tag_ <_select_> foi nomeada como “dias_da_semana”: <_select name=_"dias_da_semana">. Essa _tag_ é fechada com </_select_>. Dentro da _tag_ <_select_> temos as opções a serem selecionadas; no caso, as opções possuem como valor (_value_) os dias da semana <_option_ _value=_"segunda">Segunda-Feira</_option_>.

- áreas de texto: permitem que usuários insiram textos com várias linhas e são criadas com a _tag_ <textarea>. Exemplo (formulário de contato):

[![](https://ampli-images.s3.amazonaws.com/production/71c65e31-477c-42e3-b3f5-fe73046dc758/original)](https://ampli-images.s3.amazonaws.com/production/71c65e31-477c-42e3-b3f5-fe73046dc758/original)

- botões: botões permitem diversos tipos de ação e podem ser integrados por meio de _scripts_. São criados com a _tag_ <_button_>.

[![](https://ampli-images.s3.amazonaws.com/production/f062eb14-2e2c-4603-90d2-ee1f0fe3ae05/original)](https://ampli-images.s3.amazonaws.com/production/f062eb14-2e2c-4603-90d2-ee1f0fe3ae05/original)

- rótulos: inseridos com a _tag_ <_label_>, permitem a identificação de partes dos formulários.

[![](https://ampli-images.s3.amazonaws.com/production/4995d67a-e879-4ab2-a39a-70566bd1f89d/original)](https://ampli-images.s3.amazonaws.com/production/4995d67a-e879-4ab2-a39a-70566bd1f89d/original)

O código a seguir apresenta um exemplo de formulário contendo as opções de dias da semana. Observe que o resultado do código apresentado gera o resultado ilustrado na figura abaixo ( Elementos de formulários: menu de seleção, área de texto e botão (à esquerda). À direita é exibido o menu de seleção quando clicado).

[![](https://ampli-images.s3.amazonaws.com/production/d356dac0-a657-4692-b202-c1f7a4396e70/original)](https://ampli-images.s3.amazonaws.com/production/d356dac0-a657-4692-b202-c1f7a4396e70/original)

[![](https://ampli-images.s3.amazonaws.com/production/58c1e1f0-3653-458e-8983-82c55a724c22/original)](https://ampli-images.s3.amazonaws.com/production/58c1e1f0-3653-458e-8983-82c55a724c22/original)

Formulário com opções de dias da semana. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/b6824508-a892-450c-9626-d8d00c778585/original)](https://ampli-images.s3.amazonaws.com/production/b6824508-a892-450c-9626-d8d00c778585/original)

Elementos de formulários: menu de seleção, área de texto e botão (à esquerda). À direita é exibido o menu de seleção quando clicado. Fonte: Elaborado pelo autor.

Elementos de formulários: menu de seleção, área de texto e botão (à esquerda). À direita é exibido o menu de seleção quando clicado. Fonte: Elaborado pelo autor.

- entradas: são o tipo de elemento mais importante em formulários. Elas são inseridas usando-se a _tag_ <_input_>, por exemplo:

[![](https://ampli-images.s3.amazonaws.com/production/0ab457c0-4636-4ff7-a210-fef8fcf726a2/original)](https://ampli-images.s3.amazonaws.com/production/0ab457c0-4636-4ff7-a210-fef8fcf726a2/original)

A _tag_ <_input_> pode ter diversos tipos (especificados no atributo _type_), como caixas de texto, senhas, caixas de seleção múltiplas e únicas, entre outros.

# **Tipos de entrada e atributos**

[![](https://ampli-images.s3.amazonaws.com/production/1d717ca9-346c-4aea-a52e-8ee9acd80024/original)](https://ampli-images.s3.amazonaws.com/production/1d717ca9-346c-4aea-a52e-8ee9acd80024/original)

A _tag_ <_input_> recebe uma série de atributos que definirão o tipo dos dados que serão submetidos como entrada. Observe a figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/72ab4862-a52f-4cdb-a385-7925cacbe6ca/original)](https://ampli-images.s3.amazonaws.com/production/72ab4862-a52f-4cdb-a385-7925cacbe6ca/original)

[![](https://ampli-images.s3.amazonaws.com/production/b213fedb-6fca-4d57-96ab-8b7e6e6f749c/original)](https://ampli-images.s3.amazonaws.com/production/b213fedb-6fca-4d57-96ab-8b7e6e6f749c/original)

[![](https://ampli-images.s3.amazonaws.com/production/b9fc8e17-a1a1-4840-a8ee-8caaf75a08e4/original)](https://ampli-images.s3.amazonaws.com/production/b9fc8e17-a1a1-4840-a8ee-8caaf75a08e4/original)

Tipos de input. Fonte: Adaptado de Mariano (2020); W3C (2012).

**📝 Exemplificando**

**Aplicação dos elementos em HTML5**

No exemplo a seguir, implementaremos todos os tipos de elementos de entrada em um formulário:

[![](https://ampli-images.s3.amazonaws.com/production/00c37ef3-6ec6-43bd-90ee-957a4d7058cc/original)](https://ampli-images.s3.amazonaws.com/production/00c37ef3-6ec6-43bd-90ee-957a4d7058cc/original)

[![](https://ampli-images.s3.amazonaws.com/production/e266d058-0b00-4e27-824b-668b78c8ae0c/original)](https://ampli-images.s3.amazonaws.com/production/e266d058-0b00-4e27-824b-668b78c8ae0c/original)

[![](https://ampli-images.s3.amazonaws.com/production/d390a50c-1bcd-445f-a1a2-ba35a7a0b104/original)](https://ampli-images.s3.amazonaws.com/production/d390a50c-1bcd-445f-a1a2-ba35a7a0b104/original)

[![](https://ampli-images.s3.amazonaws.com/production/2991bb65-1f1c-4091-a90f-6ef70a74c92d/original)](https://ampli-images.s3.amazonaws.com/production/2991bb65-1f1c-4091-a90f-6ef70a74c92d/original)

Formulário com todos os elementos de entrada. Fonte: Elaborado pelo autor.

Observe, a seguir, a página construída ilustrada.

[![](https://ampli-images.s3.amazonaws.com/production/00b900e6-3a09-4afe-ac9b-0d733eb30371/original)](https://ampli-images.s3.amazonaws.com/production/00b900e6-3a09-4afe-ac9b-0d733eb30371/original)

Tipos de elementos input. Fonte: Captura de tela da página Formulários elaborada pelo autor.

Agora, vamos, então, analisar alguns desses elementos.

# **Caixas de texto e senhas**

[![](https://ampli-images.s3.amazonaws.com/production/9ac1e04c-3914-4dcb-87b7-9eaa02a09c90/original)](https://ampli-images.s3.amazonaws.com/production/9ac1e04c-3914-4dcb-87b7-9eaa02a09c90/original)

As caixas de texto (_type text_) são os elementos de entrada mais comuns. Esse tipo de _input_ gera uma caixa de texto de linha única em que o usuário poderá digitar qualquer tipo de informação. As caixas de texto de senhas (_type password_) são bastante similares a elas. A principal diferença é que nos _inputs_ do tipo _password_, o texto é criptografado diretamente quando digitado. Observe o exemplo da figura abaixo (_Inputs_ dos tipos _text_ e _password_. Ao digitar no campo do tipo _password_, os caracteres são exibidos como marcadores).

[![](https://ampli-images.s3.amazonaws.com/production/6ac5eb7a-5501-41ce-8d79-322576ee5c90/original)](https://ampli-images.s3.amazonaws.com/production/6ac5eb7a-5501-41ce-8d79-322576ee5c90/original)

[![](https://ampli-images.s3.amazonaws.com/production/f3edd23f-f0f9-4dd2-8a69-f1ab8f829578/original)](https://ampli-images.s3.amazonaws.com/production/f3edd23f-f0f9-4dd2-8a69-f1ab8f829578/original)

Inputs dos tipos text e password. Ao digitar no campo do tipo password, os caracteres são exibidos como marcadores. Fonte: Elaborado pelo autor.

Ambas as entradas aceitam diversos atributos, como o atributo _value_, em que se pode inserir os valores padrão para o campo, ou o atributo _placeholder_, que exibe um texto informativo no campo (esse texto desaparece quando o usuário clica na caixa de texto).

# **Botões**

[![](https://ampli-images.s3.amazonaws.com/production/52bd2a6a-fdc8-45e4-8654-2e4cf4d7bd68/original)](https://ampli-images.s3.amazonaws.com/production/52bd2a6a-fdc8-45e4-8654-2e4cf4d7bd68/original)

Além do elemento <_button_>, HTML fornece duas outras formas de criação de botões. A primeira delas é utilizando-se o _input_ do tipo _button_. A outra forma de gerar um botão é utilizando um _input_ do tipo _submit_. Entretanto, o botão do tipo _submit_ tem a função específica de enviar o formulário para a página indicada no atributo _action_ de _form_, conforme a figura abaixo (Tipos _button_ e _submit_).

[![](https://ampli-images.s3.amazonaws.com/production/685d793f-832f-4c25-93ed-29f8974a4425/original)](https://ampli-images.s3.amazonaws.com/production/685d793f-832f-4c25-93ed-29f8974a4425/original)

[![](https://ampli-images.s3.amazonaws.com/production/ba28ceac-d4d6-4e40-b5b5-948f6b3f1d14/original)](https://ampli-images.s3.amazonaws.com/production/ba28ceac-d4d6-4e40-b5b5-948f6b3f1d14/original)

Tipos button e submit. Fonte: Elaborada pelo autor.

# **Caixas de seleção únicas e múltiplas**

[![](https://ampli-images.s3.amazonaws.com/production/3090149c-707d-4caa-a533-2f027bf4c7c0/original)](https://ampli-images.s3.amazonaws.com/production/3090149c-707d-4caa-a533-2f027bf4c7c0/original)

As caixas de seleção permitem que usuários escolham certas opções. Elas são divididas em dois tipos: caixas de seleção únicas (_radio_), caracterizadas por seu formato circular, e caixas de seleção múltiplas (_checkbox_), caracterizadas pelo seu formato quadrangular.

[![](https://ampli-images.s3.amazonaws.com/production/5d517e24-c3e8-4c0e-8995-8958afcb5719/original)](https://ampli-images.s3.amazonaws.com/production/5d517e24-c3e8-4c0e-8995-8958afcb5719/original)

Código de seleção múltipla. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/2d5ecd7a-fbce-456c-9d93-a3cd3a71f776/original)](https://ampli-images.s3.amazonaws.com/production/2d5ecd7a-fbce-456c-9d93-a3cd3a71f776/original)

Código de seleção única. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/4f76dce2-3724-46ac-8152-3d09ec86113b/original)](https://ampli-images.s3.amazonaws.com/production/4f76dce2-3724-46ac-8152-3d09ec86113b/original)

Caixas de seleção múltiplas (checkbox) e únicas (radio). Fonte: Elaborado pelo autor.

Perceba que cada entrada apresenta um mesmo valor para o atributo name. Isso indica à página de processamento que os campos de seleção representam uma mesma variável. A diferença entre os campos será dada pelo valor existente no atributo _value_. Nos códigos de seleção múltipla e única apresentados, observe que a variável múltiplo recebe os valores [1, 2, 3], enquanto a variável única recebe o valor 2.

# **Novos recursos do HTML5 para formulários**

[![](https://ampli-images.s3.amazonaws.com/production/846ce801-576b-4c03-b1ac-9abdef461120/original)](https://ampli-images.s3.amazonaws.com/production/846ce801-576b-4c03-b1ac-9abdef461120/original)

HTML5 apresentou novos tipos de entradas para formulários, como os _inputs_ dos tipos _date_ e _color_. O tipo _date_ fornece um campo que, quando clicado, exibe um calendário que permite ao usuário selecionar uma data. A figura abaixo ilustra o resultado da utilização do _input_ do tipo _date_.

[![](https://ampli-images.s3.amazonaws.com/production/ea53e161-3837-45bd-ae3b-3c1de864fc4e/original)](https://ampli-images.s3.amazonaws.com/production/ea53e161-3837-45bd-ae3b-3c1de864fc4e/original)

Input do tipo date. Fonte: Captura de tela da página Formulários elaborada pelo autor.

Já as entradas do tipo color permitem que o usuário selecione uma cor. Esse elemento retorna um código de cores RGB, como vemos na figura a abaixo (_Input_ do tipo color).

[![](https://ampli-images.s3.amazonaws.com/production/77721c35-9927-46bf-a716-89fa0c56d00a/original)](https://ampli-images.s3.amazonaws.com/production/77721c35-9927-46bf-a716-89fa0c56d00a/original)

[![](https://ampli-images.s3.amazonaws.com/production/6faf37e2-60ee-4885-8565-883b47431e56/original)](https://ampli-images.s3.amazonaws.com/production/6faf37e2-60ee-4885-8565-883b47431e56/original)

Input do tipo colo. Fonte: Captura de tela da página Formulários elaborada pelo autor.

Teste as _tags_ <_inpu__t type="date_"> e <_input type="color_"> utilizando a ferramenta _Trinket_.

Chegamos ao final de uma unidade. O aprendizado foi grande e você conheceu a linguagem HTML. Agora, você pode iniciar seus projetos de páginas WEB, aplicar os conhecimentos e criar estruturas de páginas e formulários em HTML.

Bom trabalho!

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)

Conforme a situação-problema apresentada, você ficou responsável por construir uma página por meio da qual os clientes da empresa de planos de internet poderão entrar em contato com o estabelecimento.

Para construir uma página de contato usando apenas HTML, seu código-fonte deve ficar da seguinte forma:

[![](https://ampli-images.s3.amazonaws.com/production/0fdfb9b7-698d-42aa-b4c8-ae6a3eea4cda/original)](https://ampli-images.s3.amazonaws.com/production/0fdfb9b7-698d-42aa-b4c8-ae6a3eea4cda/original)

Vamos, então, analisar cada parte do código. Inicialmente é feita a declaração do cabeçalho:

[![](https://ampli-images.s3.amazonaws.com/production/b63c8400-6a13-4eb6-aea8-d109dc6c8095/original)](https://ampli-images.s3.amazonaws.com/production/b63c8400-6a13-4eb6-aea8-d109dc6c8095/original)

[![](https://ampli-images.s3.amazonaws.com/production/f61a6477-4815-412a-aaf9-7bb2b359b5d0/original)](https://ampli-images.s3.amazonaws.com/production/f61a6477-4815-412a-aaf9-7bb2b359b5d0/original)

[![](https://ampli-images.s3.amazonaws.com/production/a9ed6170-8022-407f-8009-ced2790f015c/original)](https://ampli-images.s3.amazonaws.com/production/a9ed6170-8022-407f-8009-ced2790f015c/original)

[![](https://ampli-images.s3.amazonaws.com/production/71d6bc8a-5789-497e-b791-9c752b67a0b4/original)](https://ampli-images.s3.amazonaws.com/production/71d6bc8a-5789-497e-b791-9c752b67a0b4/original)

Análise código-fonte. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/ec251c90-254d-4e8e-8af9-a2619236bc13/original)](https://ampli-images.s3.amazonaws.com/production/ec251c90-254d-4e8e-8af9-a2619236bc13/original)

Formulário de contato construído usando apenas HTML. Fonte: Captura de tela da página Formulários elaborada pelo autor.

Observe que o código apresentado apresenta alguns novos atributos; são eles: _size, cols_ e _rows_.

_Size_ altera o tamanho da entrada do tipo _text_. Observe que os campos e-mail e telefone apresentam o tamanho padrão. Apenas os campos nome e assunto foram alterados para ficarem com um tamanho maior.

O elemento _textarea_ recebe os outros dois atributos. _Cols_ determina a quantidade de colunas permitidas (tem um efeito similar ao _size_), enquanto _rows_ determina a quantidade de linhas que a área de texto deverá ter (no exemplo, cinco linhas).

É notável, ainda, que o formulário de contato construído apenas com HTML apresenta diferenças visuais quando comparado ao formulário modelo (figura: Exemplo de formulário de contato), uma vez que este aplicou folhas de estilo personalizadas (CSS), que veremos em outra oportunidade.

# **Referências**

[![](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)

**COMO a internet funciona?** [_S.l.: s.n._], 2020. 1 vídeo (6:56 min.). Publicado pelo canal Diego Mariano. Disponível em: <https://bit.ly/2My70qd>. Acesso em: 30 jul. 2021.

GOURLEY, D. _et al._ _**HTTP: the definitive guide**__._ [_S.l._]: O’Reilly Media, 2002.

GUPTA, G. _**Mastering HTML5 Forms.**_ Birmingham: Packt Publishing, 2013.

**IMAGENS**. [_S.l.: s.n._], 2017. 1 vídeo (3:05 min.). Publicado pelo canal Diego Mariano. Disponível em: <https://bit.ly/3oQuyUr>. Acesso em: 30 jul. 2021.

LAMBERT, L. _et al._ _**The Internet: a historical encyclopedia**_. [_S.l._]: ABC-CLIO, 2005.

**LINKS.** [_S.l.: s.n._], 2017. 1 vídeo (3:35 min.). Publicado pelo canal Diego Mariano. Disponível em: <https://bit.ly/36JIBop>. Acesso em: 30 jul. 2021.

MARIANO, D. **Fundamentos do HTML.** Diegomariano, 12 ago. 2020a. Disponível em: <https://bit.ly/3azuSld>. Acesso em: 30 jul. 2021.

MARIANO, D. **Introdução ao HTML.** Diegomariano, 13 ago. 2020b. Disponível em: <https://bit.ly/3cOmBMS>. Acesso em: 30 jul. 2021.

MARIANO, D. **Tags HTML5.** 2020. Disponível em: <https://bit.ly/2MVQOij>. Acesso em: 30 jul. 2021.

MARIANO, D. **Tags HTML5.** Diegomariano, 31 ago. 2020. Disponível em: <https://diegomariano.com/tags-html/>. Acesso em: 30 jul. 2021.

MARIANO, D.; DE MELO-MINARDI, R. **Introdução à programação web para bioinformática: html, css, php and javascript.** [_S.l_.]: Independently Published, 2017.

MARIANO, D.; DE MELO-MINARDI, R. **Introdução à programação web para bioinformática: HTML, CSS, PHP & JavaScript.** Belo Horizonte: [_s.n._], 2017.

MARIANO, D.; DE MELO-MINARDI, R. **Introdução à programação web para bioinformática: html, css, php and javascript.** [S.l.]: Independently Published, 2017.

**O QUE é um Website?** [_S.l.: s.n._], 2020. 1 vídeo (5:28 min.). Publicado pelo canal Diego Mariano. Disponível em: <https://bit.ly/3rraz0j>. Acesso em: 30 jul. 2021.

SILVA, M. S. **Fundamentos de HTML5 e CSS3.** São Paulo: Novatec Editora, 2018.

SILVA, M. S. **Fundamentos de HTML5** e CSS3. São Paulo: Novatec Editora, 2018.

**TAGS**. [_S.l.: s.n._], 2017. 1 vídeo (5:14 min.). Publicado pelo canal Diego Mariano. Disponível em: https://bit.ly/3oNYYXn. Acesso em: 30 jul. 2021.

TITTEL, E.; NOBLE, J.; COUTO, E. **HTML, XHTML e CSS Para Leigos.** Tradução de Elda Couto. Rio de Janeiro: Alta Books, 2018.

W3C WORKING DRAFT. _**HTML: the markup language (an HTML language reference)**_. [s.d.]. Disponível em: <https://bit.ly/3pOldxK>. Acesso em: 30 jul. 2021.

W3C WORKING DRAFT. _**HTML: the markup language (an HTML language reference).**_ [s.d]. Disponível em: <https://bit.ly/3tp54kx>. Acesso em: 30 jul. 2021.

W3SCHOOLS. _**HTML <form> enctype Attribute**_. [s.d.] Disponível em: <https://bit.ly/3tvlvMg>. Acesso em: 30 jul. 2021.