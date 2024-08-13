**SQL – Structured Query Language**

SQL é atualmente a principal linguagem utilizada para realizar consultas e manipulações de dados em Sistemas de Gerenciamento de Bancos de Dados Relacionais.

A primeira versão da linguagem foi apresentada pela IBM em 1974 com o nome Structured English Query Language (Sequel) e disponibilizada para um protótipo de banco de dados relacional denominado SEQUEL-XRM.

Em 1977, a IBM lançou um novo protótipo denominado SYSTEM/R e, ao final deste, havia desenvolvido uma linguagem que permitia acesso fácil a múltiplas tabelas, uma linguagem de quarta geração (4GL), que passou a ser denominada de SQL (Structured Query Language).

Alguns anos depois, em 1979, um grupo de desenvolvedores que havia participado do projeto SYSTEM/R fundou uma empresa – a Relational Software Inc. – responsável pelo lançamento do primeiro Sistema de Gerenciamento de Banco de Dados Relacional comercialmente viável. Esta empresa mais tarde teve o seu nome alterado para Oracle.

A linguagem SQL é composta basicamente por quatro subconjuntos:

- DDL – Data Definition Language
- DML – Data Manipulation Language
- DQL – Data Query Language
- DCL – Data Control Language

Durante o seu curso você terá outras disciplinas que abordarão com detalhes cada um dos comandos utilizados pelos quatro subconjuntos da SQL.No entanto, você terá agora a oportunidade de conhecer alguns comandos relacionados ao que foi apresentado nas aulas anteriores quando foram listadas as operações da álgebra relacional.

**Seleção**

Conforme observado na aula 15, esta operação, indicada pela letra grega σ (sigma), produz uma nova relação ou tabela apenas com as tuplas (linhas) da primeira relação que satisfazem a uma determinada condição (também chamada de predicado).

Tomando-se como exemplo a seguinte tabela, para efetuar a **seleção** do funcionário cujo ID_FUNC = 102, devemos utilizar a expressão:

σ ID_FUNC=102 (FUNCIONARIO)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122131/a19i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122131/a19i01_md80_100.jpg)

A expressão acima pode ser escrita na linguagem SQL da seguinte forma: **SELECT * FROM FUNCIONARIO WHERE ID_FUNC = 102;**

Observa-se, portanto, que nesta linguagem utilizamos a palavra reservada **SELECT** no lugar da letra grega σ (sigma). O símbolo ***** é utilizado quando queremos que sejam apresentados os dados de todas as colunas da tabela.

A preposição **FROM** é utilizada antes de informarmos o nome da tabela consultada: **FUNCIONARIO**.

Na sequência, temos a condição, isto é, queremos que sejam apresentados os dados do funcionário cujo ID_FUNC é igual a 102. Expressamos isso com o seguinte predicado: **WHERE ID_FUC = 102**. A execução do comando acima produzirá o seguinte resultado:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122132/a19i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122132/a19i02_md80_100.jpg)

**Projeção**

Muitas vezes não desejamos que sejam apresentados todos os dados que satisfazem a determinada condição. No exemplo considerado, uma hipótese seria apresentar apenas o NOME do funcionário cujo ID_FUNC é igual a 102. Neste caso, devemos **projetar** a coluna. Na SQL informamos os nomes das colunas que queremos projetar logo após o comando SELECT. Observe: **SELECT NOME_FUNC FROM FUNCIONARIO WHERE ID_FUNC = 102;**

A execução do comando acima produzirá o seguinte resultado:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122134/a19i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122134/a19i03_md80_100.jpg)

Para projetar mais de uma coluna, separamos seus nomes utilizando vírgulas: **SELECT NOME_FUNC, CARGO FROM FUNCIONARIO WHERE ID_FUNC = 102;**

A execução do comando acima produzirá o seguinte resultado:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122135/a19i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122135/a19i04_md80_100.jpg)

Mas qual comando deve ser utilizado para projetar TODOS os nomes dos funcionários? Neste caso, basta omitir a condição expressa no final. Observe: **SELECT NOME_FUNC FROM FUNCIONARIO;**

A execução do comando acima produzirá o seguinte resultado:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122136/a19i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122136/a19i05_md80_100.jpg)

**Produto cartesiano**

O produto cartesiano de duas tabelas ou relações é uma terceira tabela contendo todas as combinações possíveis entre as tuplas ou linhas da primeira e as tuplas da segunda tabela.

Observe novamente o exemplo apresentado na aula 16, o produto cartesiano das tabelas GRUPO_SP e GRUPO_RJ:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122137/a19i06_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122137/a19i06_md80_100.jpg)

A representação, conforme a álgebra relacional, do produto cartesiano acima é a seguinte:

**(GRUPO_SP) X (GRUPO_RJ)**

Quando trabalhamos com a SQL, o produto cartesiano de duas tabelas é obtido por meio da operação denominada **CROSS JOIN**. Observe:

**SELECT TIME_SP, TIME_RJ FROM GRUPO_SP CROSS JOIN GRUPO_RJ;**

A operação de junção, conforme veremos a seguir, é uma derivação do produto cartesiano.

**Junção (normal)**

A operação de junção utiliza as operações de seleção e produto cartesiano para produzir uma combinação entre as tuplas (linhas) de uma tabela com as tuplas correspondentes de outra tabela que obedecem a uma condição.

Observe novamente o exemplo apresentado na aula 18:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122139/a19i07_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122139/a19i07_md80_100.jpg)

A **junção** entre as tabelas DEPARTAMENTO e FUNCIONARIO deve ser representada, conforme notação da álgebra relacional, da seguinte forma:

σ **DEPARTAMENTO.CODDEPT = FUNCIONARIO.CODDEPT** **(DEPARTAMENTO X FUNCIONARIO)**

O resultado produzido será o seguinte:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122138/a19i08_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122138/a19i08_md80_100.jpg)

A expressão acima pode ser escrita na linguagem SQL da seguinte forma: **SELECT * FROM DEPARTAMENTO, FUNCIONARIO** **WHERE DEPARTAMENTO.CODDEPT = FUNCIONARIO.CODDEPT;**

**Junção (natural)**

A **junção natural**fornece o mesmo resultado da junção normal, mas sem a repetição de valores das colunas comuns às duas tabelas.

A junção natural entre as tabelas DEPARTAMENTO e FUNCIONARIO é representada, conforme notação da álgebra relacional, da seguinte forma: (DEPARTAMENTO |x| FUNCIONARIO)

Quando utilizamos a SQL, a junção natural de duas tabelas é obtida por meio da operação denominada **NATURAL INNER JOIN**. Observe: **SELECT * FROM DEPARTAMENTO NATURAL INNER JOIN FUNCIONARIO;**

A figura a seguir demonstra o resultado da operação de **junção natural** entre as duas tabelas anteriores (DEPARTAMENTO e FUNCIONARIO):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122140/a19i09_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122140/a19i09_md80_100.jpg)

Observamos nesta aula como utilizar a SQL (Structured Query Language) para realizar as seguintes operações da álgebra relacional: seleção, projeção, produto cartesiano e junção (normal e natural). Na última aula desta disciplina abordaremos as outras operações da álgebra relacional: união, diferença e intersecção.