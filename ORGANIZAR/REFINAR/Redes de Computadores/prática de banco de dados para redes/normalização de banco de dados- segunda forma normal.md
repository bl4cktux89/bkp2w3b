**2FN – Segunda Forma Normal**

Uma tabela está na Segunda Forma Normal (2FN) quando, além de estar na Primeira Forma Normal (1FN), **não contém dependências parciais**.

Uma dependência funcional parcial ocorre quando uma coluna que não faz parte da chave primária depende apenas de uma parte da chave primária COMPOSTA (veja o tópico da **aula 11**: "Dependência funcional irredutível à esquerda").

Sendo assim, toda tabela que está na Primeira Forma Normal e que possui chave primária SIMPLES (formada por uma coluna) já está na Segunda Forma Normal.

Analisando a tabela PROJETO_FUNCIONARIO (veja aula anterior), nota-se que as colunas (ou atributos) NOME_FUNC, CARGO e VL_HORA dependem apenas de uma parte da chave primária, ou seja, do ID_FUNC.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121961/a13i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121961/a13i01_md80_100.jpg)

Portanto, ao aplicarmos a Segunda Forma Normal (2FN), teremos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121963/a13i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121963/a13i02_md80_100.jpg)

A tabela PROJETO_FUNCIONARIO apresentará a seguinte estrutura após a aplicação da Segunda Forma Normal (2FN):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121962/a13i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121962/a13i03_md80_100.jpg)