**Introdução**

Até o presente momento, aprendemos a construção de um banco de dados com suas formas de modelagem, que auxiliam a compreender o modo como os dados estão distribuídos dentro de um SGBD (Sistema de Gerenciamento de Banco de Dados). Utilizamos também suas regras de normalização com a engenharia reversa para eliminar as redundâncias e facilitar os meios de acesso aos dados.

Os processos de busca dos dados estão fundamentados na álgebra relacional.

Trata-se de uma linguagem formal utilizada nos SGBDs para consultar os dados solicitados por um usuário. Essa linguagem possui um conjunto de operações baseadas na _**teoria de conjuntos**_, que permite selecionar, unir, subtrair e projetar um conjunto de dados relacionados.

O resultado de uma consulta é visto como um conjunto de tuplas (grupos de dados pertencentes a uma linha de uma tabela).

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

**Seleção σ**

Indicada pela letra grega σ (sigma), esta operação produz uma nova relação apenas com as tuplas (linhas) da primeira relação (tabela), que satisfazem a uma determinada condição (também chamada de predicado).

A sintaxe básica é a seguinte:

σ predicado (relação)

Observe a tabela (relação) a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122012/a15i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122012/a15i01_md80_100.jpg)

Para efetuar a **seleção** do funcionário cujo ID_FUNC = 102, devemos utilizar a seguinte expressão:

σ ID_FUNC=102 (FUNCIONARIO)

A execução desta operação produzirá uma tabela ou relação que atende à condição ID_FUNC = 102. Observe:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122013/a15i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122013/a15i02_md80_100.jpg)

**Projeção π**

Esta operação, indicada pela letra grega π (pi), produz uma nova relação ou tabela com apenas alguns atributos da primeira relação, removendo as tuplas duplicadas.

A sintaxe básica é a seguinte: π nome da coluna, nome da coluna (relação)

Tomando-se ainda como base a tabela FUNCIONARIO, para efetuar a projeção da coluna NOME_ FUNC devemos utilizar a seguinte expressão: π CARGO (FUNCIONARIO) .

A execução desta operação produzirá a tabela ou relação a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122015/a15i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122015/a15i03_md80_100.jpg)

_**Note que as tuplas (linhas) repetidas foram removidas.**_

Veja agora como efetuar a projeção das colunas ID_FUNC e NOME_FUNC:

π ID_FUNC, NOME_FUNC (FUNCIONARIO)

A relação produzida pela expressão acima é a seguinte:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122014/a15i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122014/a15i04_md80_100.jpg)

Podemos também aplicar as operações de seleção e projeção em determinada relação ou tabela. No exemplo a seguir foi aplicada uma operação de seleção para obter-se a tupla (linha) cujo ID_FUNC = 102 e depois uma operação de projeção sobre a coluna NOME_FUNC.

π NOME_FUNC (σ ID_FUNC=102 (FUNCIONARIO)

O resultado da expressão acima é o seguinte:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122016/a15i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122016/a15i05_md80_100.jpg)

Na próxima aula abordaremos outra operação da álgebra relacional: o **produto cartesiano**.