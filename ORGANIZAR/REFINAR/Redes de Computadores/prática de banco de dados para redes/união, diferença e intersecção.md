**União (Union)**

A união entre duas relações ou tabelas gera uma terceira tabela com todas as tuplas ou linhas comuns e não comuns.

As tuplas comuns às duas relações aparecerão apenas uma vez no resultado.As duas tabelas devem ter o mesmo número de atributos ou colunas e mesmos domínios para as colunas correspondentes.

Na álgebra relacional, para efetuar a **união** das tabelas CLIENTE_1 e CLIENTE_2, utilizamos a expressão: (CLIENTE_1) U (CLIENTE_2)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122184/a20i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122184/a20i01_md80_100.jpg)

Na SQL devemos utilizar o operador denominado **UNION** da seguinte forma:

**SELECT CODIGO, NOME FROM CLIENTE_1**

**UNION**

**SELECT CODIGO, NOME FROM CLIENTE_2;**

A execução do comando acima produzirá o seguinte resultado:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122186/a20i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122186/a20i02_md80_100.jpg)

**Diferença (Minus)**

A diferença entre duas tabelas produz uma nova com todas as linhas da primeira tabela que não aparecem na segunda.

As duas tabelas devem ter o mesmo número de colunas e mesmos domínios para as colunas correspondentes.

Na álgebra relacional, para efetuar a **diferença** entre as tabelas CLIENTE_1 e CLIENTE_2, utilizamos a expressão: (CLIENTE_1) - (CLIENTE_2)

Na SQL devemos utilizar o operador denominado **MINUS** da seguinte forma:

**SELECT CODIGO, NOME FROM CLIENTE_1**

**MINUS**

**SELECT CODIGO, NOME FROM CLIENTE_2;**

A execução do comando acima produzirá o seguinte resultado:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122185/a20i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122185/a20i03_md80_100.jpg)

Devemos lembrar que a operação de diferença não é comutativa:

(CLIENTE_1) - (CLIENTE_2) é diferente de (CLIENTE_2) - (CLIENTE_1)

Observe a seguir o resultado de:

**SELECT CODIGO, NOME FROM CLIENTE_2**

**MINUS**

**SELECT CODIGO, NOME FROM CLIENTE_1;**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122188/a20i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122188/a20i04_md80_100.jpg)

**Intersecção (Intersect)**

A intersecção entre duas tabelas produz uma nova tabela na qual somente aparecerão as linhas em comum entre a primeira e a segunda tabela escritas uma única vez.

Neste caso, as duas relações também devem ter o mesmo número de atributos e mesmos domínios para as colunas correspondentes.Na álgebra relacional, para efetuar a **intersecção** entre as tabelas CLIENTE_1 e CLIENTE_2, utilizamos a expressão:

(CLIENTE_1) ∩ (CLIENTE_2)

Na SQL devemos utilizar o operador denominado **INTERSECT** da seguinte forma:

**SELECT CODIGO, NOME FROM CLIENTE_1**

**INTERSECT**

**SELECT CODIGO, NOME FROM CLIENTE_2;**

A execução do comando acima produzirá o seguinte resultado:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122187/a20i05md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122187/a20i05md80_100.jpg)

As duas últimas aulas apresentaram uma breve introdução à SQL (Structured Query Language). O principal objetivo foi comparar as operações da álgebra relacional com os comandos SQL correspondentes.

Há, sem dúvida, muito mais a ser considerado sobre esta linguagem utilizada pela maioria dos bancos de dados relacionais. Mas isto será assunto para outra disciplina que será oferecida em um dos próximos semestres do seu curso. Aguarde!