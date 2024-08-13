**Introdução**

Conforme você aprendeu na aula anterior, a normalização envolve um conjunto de regras aplicadas em um banco de dados com a finalidade de corrigir redundâncias, separando os dados até que seus atributos apresentem valores atômicos, isto é, indivisíveis.

Nesta e nas próximas duas aulas abordaremos as seguintes formas normais:

- Primeira Forma Normal (1FN).
- Segunda Forma Normal (2FN).
- Terceira Forma Normal (3FN).

**Primeira Forma Normal (1FN)**

Uma tabela se encontra na Primeira Forma Normal (1FN) quando **não possui tabelas aninhadas**, ou seja, quando uma ocorrência de uma tabela possui dentro dela um subconjunto de atributos multivalorados, isto é, com mais de um valor, caracterizando outra tabela interna.

Para que uma tabela esteja na 1FN, é necessário que cada atributo de uma ocorrência tenha apenas um valor.

Observe o seguinte exemplo:

Uma empresa de engenharia utiliza os formulários apresentados a seguir para controle de seus projetos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121932/a12i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121932/a12i01_md80_100.jpg)

Para registrar os dados dos seus projetos, a empresa adotou planilhas eletrônicas com a seguinte estrutura:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121933/a12i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121933/a12i02_md80_100.jpg)

No entanto, à medida que a quantidade de projetos e funcionários alocados neles cresceu, observou-se que seria necessário utilizar um sistema de banco de dados. Para garantir a integridade e controlar a redundância dos dados, aplicou-se à tabela acima a Primeira Forma Normal (1FN).

A tabela para controle de projetos apresenta a seguinte tabela aninhada:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121934/a12i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121934/a12i03_md80_100.jpg)

Não se deve simplesmente separar a tabela acima do restante da tabela de controle de projetos, porque, neste caso, não seria mais possível determinar em quais projetos cada funcionário trabalhou. Para que isso não ocorra, é preciso incluir a coluna NR_PROJ na tabela que será denominada PROJETO_FUNCIONARIO:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121935/a12i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121935/a12i04_md80_100.jpg)

Consequentemente, a segunda tabela (PROJETO) apresentará a seguinte estrutura:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121936/a12i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/9/121936/a12i05_md80_100.jpg)

Observe que após a aplicação da Primeira Forma Normal (1FN) não temos mais tabelas aninhadas. Outro detalhe: os usuários terão acesso às mesmas informações anteriormente disponibilizadas na tabela que não estava na Primeira Forma Normal.