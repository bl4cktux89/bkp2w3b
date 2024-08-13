**Terceira Forma Normal (3FN)**

Uma tabela está na Terceira Forma Normal (3FN) quando, além de estar na 2FN (Segunda Forma Normal), **não contém dependências transitivas**.

Uma dependência funcional transitiva ocorre quando uma coluna, além de depender da chave primária da tabela, depende diretamente de outra(s) coluna(s) da tabela. (veja o tópico da aula **11**: "Dependência Funcional Transitiva").

A tabela FUNCIONARIO apresenta uma dependência funcional transitiva. Observe que o VL_HORA não depende diretamente do ID_FUNC. VL_HORA depende diretamente do CARGO.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121992/a14i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121992/a14i01_md80_100.jpg)

Portanto, ao aplicar-se a Terceira Forma Normal (3FN), teremos uma tabela que pode ser denominada CARGO_SALARIO com a seguinte estrutura:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121993/a14i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121993/a14i02_md80_100.jpg)

A tabela FUNCIONARIO, após a aplicação da Terceira Forma Normal, apresentará a estrutura a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121994/a14i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121994/a14i03_md80_100.jpg)

Observe, a seguir, quais foram as tabelas geradas após a aplicação das três primeiras Formas Normais (FN1, FN2 e FN3) e compare com a tabela controle de projeto anteriormente apresentada (veja aula 12).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121995/a14i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121995/a14i04_md80_100.jpg)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121996/a14i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121996/a14i05_md80_100.jpg)

**IMPORTANTE**

O exemplo apresentado tem objetivo exclusivamente didático para esclarecimento dos conceitos envolvidos na aplicação de cada uma das três primeiras Formas Normais. Outros detalhes deveriam ser levados em consideração para o desenvolvimento de um sistema completo, por exemplo, armazenar os valores históricos dos salários, quantidade de horas de cada funcionário nos respectivos projetos etc.