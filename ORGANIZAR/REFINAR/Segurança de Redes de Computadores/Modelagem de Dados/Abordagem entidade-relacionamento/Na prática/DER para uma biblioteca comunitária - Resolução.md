[![](https://ampli-images.s3.amazonaws.com/production/e46a6901-e804-47bd-9902-dbd38e84ec49/original)](https://ampli-images.s3.amazonaws.com/production/e46a6901-e804-47bd-9902-dbd38e84ec49/original)

Observe que, por ser um centro comunitário, possivelmente não haverá verbas para a compra de licença de softwares. O ideal é instalar um sistema operacional Linux e um SGBD freeware, como o Kexi ou o Base (concorrentes das versões proprietárias, como o Access), e que, além de criar o banco de dados, permitem criar telas intuitivas para usuários leigos. Para ajudar no controle de empréstimos dos livros, poderá ser desenvolvido um banco de dados pequeno. O modelo lógico textual do banco de dados ficará da seguinte forma:

Livro (**\#codLivro**, Título, &codTipoLivro, &IdAutor, &IdEditora)

Tipo de Livro (**\#codTipoLivro**, Tipo de Livro)

Autor (**\#IdAutor**, Nome) Editora (\#IdEditora, Editora)

Pessoa (**\#matrículaPessoa**, Nome, Dt Nasc, Nome Responsável, Endereço, foto)

Empréstimo (**\#CodEmpréstimo**, DtRetirada, DtDevolução, &codLivro, & matrícula Pessoa)

Como sugestão, você poderá:

- Pesquisar e criar uma versão gráfica das tabelas e dos campos listados na versão textual do modelo lógico do banco de dados.
- Criar o dicionário de dados de todas as tabelas mostradas na versão textual do modelo lógico do banco de dados.