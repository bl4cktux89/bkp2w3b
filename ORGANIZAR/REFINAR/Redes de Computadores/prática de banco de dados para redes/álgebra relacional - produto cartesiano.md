**Produto cartesiano X**

O produto cartesiano (representado por X) de duas tabelas ou relações é uma terceira relação contendo todas as combinações possíveis entre as tuplas (linhas) da primeira e as tuplas da segunda tabela.A sintaxe básica é a seguinte:

(relação 1) X (relação2)

A figura a seguir demonstra como é realizada a operação entre duas tabelas genéricas TABELA_1 e TABELA_2:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122038/a16i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122038/a16i01_md80_100.jpg)

Concluímos, portanto, que o produto cartesiano de uma tabela formada por três colunas e quatro linhas com outra formada por duas colunas e três linhas será uma terceira tabela com a seguinte estrutura:

3 colunas + 2 colunas = **5 colunas**

4 linhas x 3 linhas = **12 linhas**

Analisaremos agora um exemplo prático. Imagine que em determinado campeonato de futebol entre os principais times dos estados de São Paulo e do Rio de Janeiro foram formados dois grupos com quatro times em cada grupo. Os times de um estado deverão enfrentar os times do outro. Aplicando-se a operação da álgebra relacional denominada produto cartesiano teremos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122039/a16i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/2/0/122039/a16i02_md80_100.jpg)

O produto cartesiano, embora na prática não tenha muitas aplicações diretas, é uma forma primitiva utilizada para juntar informações de duas tabelas para posterior processamento. A operação de junção, conforme veremos nas aulas seguintes, é uma derivação do produto cartesiano. Aplica-se, neste caso, uma operação de seleção para obter apenas as combinações que realmente interessam.