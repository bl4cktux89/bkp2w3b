**União U**

O resultado da união entre duas relações ou tabelas gera uma terceira relação com todas as tuplas (linhas) comuns e não comuns.

As tuplas comuns às duas relações aparecerão apenas uma vez no resultado.As duas relações devem ter o mesmo número de atributos (colunas) e mesmos domínios para as colunas correspondentes.

A sintaxe básica é a seguinte:

(relação 1) U (relação 2). A figura a seguir demonstra como é realizada a operação de **união** entre duas tabelas genéricas TABELA_1 e TABELA_2:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122089/a17i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122089/a17i01_md80_100.jpg)

**Diferença -**

A diferença entre duas relações produz uma nova relação com todas as tuplas da primeira relação que não aparecem na segunda relação.As duas relações devem ter o mesmo número de atributos (colunas) e mesmos domínios para as colunas correspondentes.

A sintaxe básica é a seguinte:

(relação 1) - (relação 2)

A figura a seguir demonstra como é realizada a operação de **diferença** entre duas tabelas genéricas TABELA_1 e TABELA_2:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122090/a17i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122090/a17i02_md80_100.jpg)

É importante enfatizar que, se invertermos as tabelas, o resultado não será o mesmo; a operação não é comutativa. Exemplificando, poderíamos dizer que:

(relação 1) - (relação 2) é diferente de (relação 2) - (relação 1)

Observe a seguir o resultado de (TABELA_2) – (TABELA_1):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122091/a17i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122091/a17i03_md80_100.jpg)

**Intersecção n**

A intersecção entre duas relações produz uma nova relação entre a primeira entidade e a segunda, em que somente aparecerão as tuplas em comum escritas uma única vez.

Neste caso, as duas relações também devem ter o mesmo número de atributos e mesmos domínios para as colunas correspondentes.A sintaxe básica é a seguinte:

(relação 1) ∩ (relação 2)

A figura a seguir demonstra como é realizada a operação de **intersecção** entre duas tabelas genéricas TABELA_1 e TABELA_2:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122092/a17i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122092/a17i04_md80_100.jpg)