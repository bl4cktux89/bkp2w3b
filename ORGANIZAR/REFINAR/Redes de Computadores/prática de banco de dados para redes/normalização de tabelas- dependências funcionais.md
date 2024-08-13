**Normalização**

A normalização envolve um conjunto de regras aplicadas em um banco de dados com a finalidade de corrigir redundâncias, separando os dados até que seus atributos apresentem valores atômicos, isto é, indivisíveis.

O conceito de normalização foi introduzido em 1970 por Edgard F. Codd e baseia-se no processo matemático formal com fundamento na teoria dos conjuntos.

O processo de normalização aplica uma série de regras sobre as tabelas de um banco de dados para verificar se estas foram corretamente projetadas.

**Objetivos da normalização de tabelas**

Os objetivos principais da normalização de tabelas são os seguintes:

- Garantir a integridade dos dados, evitando que informações sem sentido sejam inseridas.
- Organizar e dividir as tabelas da forma mais eficiente possível, diminuindo a redundância e permitindo a evolução do banco de dados.

**Formas normais**

São seis as formas normais mais utilizadas:

- Primeira Forma Normal (1FN).
- Segunda Forma Normal (2FN).
- Terceira Forma Normal (3FN).
- Forma Normal de Boyce e Codd (FNBC).
- Quarta Forma Normal (4FN).
- Quinta Forma Normal (5FN).

**Nota:** Neste curso abordaremos as três primeiras formas normais, pois estas atendem à maioria dos casos de normalização.

Uma forma normal engloba todas as anteriores, isto é, para que uma tabela esteja na 2FN, ela obrigatoriamente deve estar na 1FN e assim por diante.

Normalmente, após a aplicação das regras de normalização, algumas tabelas acabam sendo divididas em duas ou mais. Este processo colabora significativamente para a estabilidade do modelo de dados e reduz consideravelmente as necessidades de manutenção.

Antes de passarmos à parte prática, aplicando as regras conforme a 1FN, 2FN e 3FN, será necessário apresentar alguns conceitos fundamentais diretamente relacionados às Formas Normais.

**Dependência Funcional (DF)**

Sempre que um atributo X identifica um atributo Y, dizemos que entre eles há uma **dependência funcional**. A representação é:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121898/a11i10_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121898/a11i10_md80_100.jpg)

Neste caso, estado é funcionalmente dependente de cidade ou ainda cidade determina estado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121909/a11i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121909/a11i01_md80_100.jpg)

**Transitividade**

Se um atributo X determina Y e se Y determina Z, podemos dizer que X determina Z de forma transitiva, isto é, existe uma dependência funcional transitiva de X para Z.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121899/a11i11_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121899/a11i11_md80_100.jpg)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121908/a11i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121908/a11i02_md80_100.jpg)

**Dependência funcional irredutível à esquerda**

O lado esquerdo de uma dependência funcional é irredutível quando o determinante está em sua forma mínima, isto é, quando não é possível reduzir a quantidade de atributos determinantes sem perder a dependência funcional.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121900/a11i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121900/a11i03_md80_100.jpg)

Não está na forma irredutível à esquerda, pois podemos ter somente o estado como determinante.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121901/a11i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121901/a11i04_md80_100.jpg)

Está na forma irredutível à esquerda.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121910/a11i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121910/a11i05_md80_100.jpg)

**Dependência Multivalorada (DMV)**

A DMV é uma ampliação da Dependência Funcional (DF). Na DMV, o valor de um atributo determina um conjunto de valores de outro atributo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121902/a11i06_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121902/a11i06_md80_100.jpg)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121903/a11i07_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121903/a11i07_md80_100.jpg)

Temos somente um nome para cada CPF

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121904/a11i08_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121904/a11i08_md80_100.jpg)

Temos vários dependentes para cada CPF

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121905/a11i09_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121905/a11i09_md80_100.jpg)