[![](https://ampli-images.s3.amazonaws.com/production/99c9b72e-e1c9-4b2d-ac1b-8ecff7f1bc02/original)](https://ampli-images.s3.amazonaws.com/production/99c9b72e-e1c9-4b2d-ac1b-8ecff7f1bc02/original)

O MySQL Workbench® é de propriedade da empresa Oracle e é uma ferramenta CASE gratuita que gera scripts para o SGBD MySQL. O foco dela é a modelagem física do banco de dados, acelerando o processo de criação da base de dados. Acesse o site para [download](https://www.mysql.com/products/workbench/).

Observe na Figura abaixo que o relacionamento utiliza a notação do “Pé-de-Galinha”.

[![](https://ampli-images.s3.amazonaws.com/production/aec6d1d5-4c68-4786-b6c5-0106bbb63c78/original)](https://ampli-images.s3.amazonaws.com/production/aec6d1d5-4c68-4786-b6c5-0106bbb63c78/original)

Exemplo ferramenta CASE MySQL Workbench. Fonte: captura de tela do MySQL Workbench, elaborada pela autora.

**📝 Exemplificando**

Para criar o diagrama da Figura acima, siga o passo a passo a seguir:

1. Vá ao Menu e escolha File → New Model → Add New Diagram.
2. Para inserir uma tabela, aperte a letra **T** e pressione enter. Dê dois cliques na tabela para abrir o editor de campos e adicione-os, juntamente com seus tipos, e insira as chaves primárias e estrangeiras.
3. Para definir os relacionamentos entre tabelas, escolha as ligações que estão na barra lateral esquerda do diagrama criado.
4. Depois de criado o diagrama, é possível exportá-lo para um script SQL ou até inseri-lo diretamente no SGBD. Acesse o menu File → Export → Forward Enginieer SQL Create Script.

_______

Ferramentas online também são uma opção para a criação de modelos gráficos de desenvolvimento de software. Draw.IO é uma ferramenta fácil, que tem como requisito estar conectado à Internet. Está disponível no [site](https://app.diagrams.net/). A ferramenta ainda disponibiliza uma grande quantidade de _templates_ de modelos para servirem de exemplos de modelagem. Na Figura abaixo, foi realizada a modelagem com a notação de setas. O uso da ferramenta é bem intuitivo: ao lado esquerdo estão as categorias de diagrama, então, você pode acessar a _Entity Relation_ para ter acesso às opções de tabela e clicar em uma delas para adicioná-la a área de trabalho. Os campos podem ser editados diretamente na tabela adicionada. Para relacionar as tabelas, escolha as opções de seta e ligue a chave primária diretamente sobre a chave estrangeira.

[![](https://ampli-images.s3.amazonaws.com/production/cce50f07-2c4a-4fab-9ebf-7b54c3e0a04f/original)](https://ampli-images.s3.amazonaws.com/production/cce50f07-2c4a-4fab-9ebf-7b54c3e0a04f/original)

Exemplo ferramenta CASE online Draw.IO. Fonte: captura de tela do Draw.IO, elaborada pela autora.

**🔁 Assimile**

Um _template_ é um exemplo ou um modelo que pode servir de base de criação para algum determinado objetivo. Possui uma estrutura predefinida que facilita o desenvolvimento e a criação do conteúdo a partir de algo que já foi construído previamente.

_______

Outra ferramenta CASE online é a [Lucidchart](https://www.lucidchart.com/pages/pt). No site, é possível criar gratuitamente um modelo com até 60 objetos, acima disso, é necessário pagar. Essa ferramenta é ideal para pequenos e médios projetos. Veja um exemplo na Figura abaixo, em que foi utilizada a notação “Pé-de-Galinha”. Na ferramenta, você utilizará os recursos da categoria padrão e entidade-relacionamentos. Na categoria de entidade-relacionamentos, você deverá selecionar o modelo de tabela que desejar e inserir os campos diretamente na figura da tabela. Para criar o relacionamento entre as tabelas, use a ferramenta de “seta” na categoria, ligando sempre a chave primária com a sua chave estrangeira (na outra tabela).

[![](https://ampli-images.s3.amazonaws.com/production/58622637-f829-4462-a85e-10ec7baca21d/original)](https://ampli-images.s3.amazonaws.com/production/58622637-f829-4462-a85e-10ec7baca21d/original)

Exemplo ferramenta CASE online Lucidchart. Fonte: captura de tela do Lucidchart, elaborada pela autora.

Um dos destaques dessa ferramenta é a possibilidade de gerar scripts para os seguintes Sistemas de Gerenciadores de Banco de Dados: MySQL, PostgreSQL, SQL Server e Oracle, conforme pode ser observado na Figura abaixo. Para gerar o script, acesse a opção “Exportar” no menu esquerdo do software, na categoria de entidade relacionamentos. Ao selecioná-la, você terá acesso à tela da Figura abaixo e poderá escolher para qual banco deseja gerar o script. Também será possível exportar o DER para uma imagem, para isso, selecione Arquivo → Baixar como → e escolha a opção que desejar.

[![](https://ampli-images.s3.amazonaws.com/production/afc4a4c2-8643-4013-949e-dae5cf81de2d/original)](https://ampli-images.s3.amazonaws.com/production/afc4a4c2-8643-4013-949e-dae5cf81de2d/original)

Exemplo exportando para SQL no Lucidchart. Fonte: captura de tela do Lucidchart, elaborada pela autora.

**📝 Exemplificando**

Um exemplo de um script gerado automaticamente após criar a tabela Estado traz o código em SQL totalmente pronto, observe:

CREATE TABLE Estado ( Sigla CHAR(2) NOT NULL, Estado CHAR(40))

_______

Um diagrama de entidade-relacionamentos geralmente possui muitas entidades, e utilizar uma ferramenta CASE para criar as tabelas e relacionamentos facilita muito o trabalho do desenvolvedor.  Agora que já conhecemos algumas ferramentas CASEs disponíveis, vejamos um estudo de caso para que possa ser implementado em uma das ferramentas:

Após diversas situações de emergência devido a inundações, geadas e vendavais, a defesa civil de uma cidade no sul do país precisa de um banco de dados com informações sobre as vítimas, para poder controlar as emergências que ocorreram e a quantidade de pessoas envolvidas. Uma emergência pode atingir cidades vizinhas e a defesa civil pode intervir em outras cidades.

Os requisitos para realizar o banco de dados são os seguintes:

- É necessário anotar o endereço da família em situação de risco.
- Deve haver um cadastro de cada membro de uma família. Os dados pessoais e uma foto são fundamentais.
- A família poderá ser classificada por tipo: em risco, alto risco, extremo risco.
- Deve haver uma tabela para cadastro das emergências classificadas em: inundação, vendaval, desmoronamentos, entre outras opções.
- Uma família pode sofrer com diversas emergências e uma emergência pode atingir diversas famílias. É necessário armazenar a data da emergência e os danos causados por ela.

Para criar o diagrama de entidade-relacionamentos, conforme a Figura abaixo, foi utilizada a ferramenta CASE online [Lucidchart](https://www.lucidchart.com/pages/pt). Acesse o site [](http://www.lucidchart.com/)e selecione o local em que deseja salvar o diagrama. Depois, escolha a opção  Arquivo → Novo Documento e selecione Entidade Relacionamento (ERD). Escolha a figura para a tabela (pode ser a que você achar mais interessante), adicione os campos diretamente da tabela, dê dois cliques nela e digite o nome e os campos da tabela. Para relacionar: crie antes todas as tabelas. No menu superior, escolha as setas para relacionar a chave primária com a sua chave estrangeira.

[![](https://ampli-images.s3.amazonaws.com/production/a3ec0ad1-0da1-4bbc-9287-412b7e3bf6a0/original)](https://ampli-images.s3.amazonaws.com/production/a3ec0ad1-0da1-4bbc-9287-412b7e3bf6a0/original)

Estudo de caso com Lucidchart. Fonte: elaborada pela autora.

**💭 Reflita**

Observe o DER da Figura acima. Na tabela Família-Emergência há o campo Danos. Os danos podem se repetir para outras famílias? Como poderemos impedir que essa repetição seja muito frequente no banco de dados?