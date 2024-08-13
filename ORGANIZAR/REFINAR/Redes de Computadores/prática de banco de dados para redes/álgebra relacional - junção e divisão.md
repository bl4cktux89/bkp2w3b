**Junção**

A operação denominada junção combina as operações de seleção e produto cartesiano produzindo uma combinação entre as tuplas de uma tabela com as tuplas correspondentes de outra tabela que obedecem a uma condição. A sintaxe básica é a seguinte: σ **relaçãoA.chave1=relaçãoB.chave2** ( relação A X relação B ).

A figura a seguir demonstra como é realizada a operação de **junção** entre duas tabelas DEPARTAMENTO e FUNCIONARIO:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122114/a18i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122114/a18i01_md80_100.jpg)

A operação de junção foi criada justamente porque esse tipo de combinação de tabelas é de uso muito comum, facilitando, assim, a escrita de expressões. A tabela resultante de uma junção tem todas as colunas da primeira tabela e todas da segunda tabela. Isso faz os valores dos campos utilizados como critério para a correspondência entre as linhas aparecerem duplicados, já que um vem da primeira tabela e outro da segunda.

**Junção natural |X|**

Existe uma variação da junção, chamada _**junção natural,**_ que fornece o mesmo resultado, mas sem essa repetição de valores: uma das colunas correspondentes aos atributos de relacionamento é descartada.

A sintaxe básica é a seguinte:

( relação A |X| relação B )

A figura a seguir demonstra como é realizada a operação de **junção natural** entre as duas tabelas anteriores (DEPARTAMENTO e FUNCIONARIO):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122116/a18i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122116/a18i02_md80_100.jpg)

**Divisão**

Produz uma nova tabela ou relação contendo todas as tuplas da primeira tabela (dividendo) que aparecem na segunda (mediador) com todas as tuplas da terceira tabela (divisor).

No exemplo apresentado a seguir, observa-se que a TABELA_S contém todas as tuplas da TABELA_1 (dividendo) que aparecem na TABELA_R (mediador) com todas as tuplas da TABELA_2 (divisor):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122117/a18i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122117/a18i03_md80_100.jpg)

O próximo exemplo apresenta o mesmo dividendo (TABELA_1) e o mesmo mediador (TABELA_R), mas agora há outro divisor (TABELA_2). Note o resultado:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122118/a18i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/1/122118/a18i04_md80_100.jpg)

As últimas quatro aulas (15, 16, 17 e 18) apresentaram as operações da álgebra relacional. Conforme mencionado (na aula 15), trata-se de uma linguagem formal utilizada nos Sistemas de Gerenciamento de Banco de Dados para consultar os dados solicitados por um usuário. A linguagem possui um conjunto de operações baseadas na _**teoria de conjuntos**_ que permite selecionar, unir, subtrair e projetar um conjunto de dados relacionados.

As operações primitivas que utilizam a álgebra relacional são:

- Seleção
- Projeção
- Produto cartesiano
- União
- Diferença

As operações derivadas que utilizam a álgebra relacional são:

- Intersecção
- Junção (normal e natural)
- Divisão

Mas não foi apresentado ainda como aplicar estas operações utilizando-se um Sistema de Gerenciamento de Banco de Dados. Esta importante etapa será abordada nas duas últimas aulas.