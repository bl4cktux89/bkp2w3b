A próxima etapa do projeto de banco de dados envolve o chamado **modelo lógico**. Atualmente, grande parte dos sistemas de banco de dados utiliza o **modelo relacional**. Um banco de dados relacional é composto por **tabelas** (também denominadas relações).

Observe a seguir alguns conceitos importantes para pleno entendimento do modelo relacional:

**Tabela**

Estrutura bidimensional composta por linhas (tuplas) e campos (ou atributos).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121834/a08i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121834/a08i01_md80_100.jpg)

**Chave primária**

Atributo por meio do qual é possível identificar determinado registro. Uma chave primária não pode ser repetida, ou seja, o conjunto de valores que constituem a chave primária deve ser único dentro de uma tabela.

**Chave primária simples:** apenas um atributo (campo) compõe a chave primária.

**Chave primária composta:** mais de um atributo compõe a chave primária.

Na aula anterior falamos sobre atributo identificador, responsável por identificar uma ocorrência na entidade. Trata-se de um atributo em que não se encontra duplicidade de dados. O atributo identificador corresponde normalmente à chave primária no modelo lógico (relacional).

Portanto, para escolher uma chave primária é preciso certificar-se de que esse atributo **não terá duplicidade**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121835/a08i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121835/a08i02_md80_100.jpg)

**Chave estrangeira**

Utilizada quando queremos que o valor de um atributo seja validado a partir do valor de atributo de outra tabela. Criamos, assim, uma relação de dependência (um relacionamento) entre as tabelas.

Observe que, no exemplo a seguir, antes de efetuar a alocação de um **funcionário** em um **departamento**, é necessário que o departamento em questão conste na tabela de departamentos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121837/a08i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121837/a08i03_md80_100.jpg)

Para que haja equivalência, o conteúdo da chave estrangeira deve ser igual ao da chave primária. O SGBD (Sistema de Gerenciamento de Banco de Dados) "liga" todos os registros em que o conteúdo da chave primária seja igual ao de sua chave estrangeira.

Para entender o processo de chave estrangeira, veja o inforgráfico abaixo. Este inforgráfico faz parte da sequência desta aula e, portanto, é essencial para a aprendizagem.

[**INFOGRÁFICO**](https://ead.uninove.br/ead/disciplinas/web/_g/md80_100/a08if01_md80_100.htm)

**Chave única (Unique)**

Utilizada quando determinado campo não deve ser repetido e não é chave primária. Aumenta a consistência do banco de dados.

Exemplo: cadastro de funcionários. Cada funcionário recebe um código único, que é a chave primária. Para maior segurança e consistência, podemos optar para que o campo CPF também seja único, evitando que o mesmo funcionário seja cadastrado duas vezes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121836/a08i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121836/a08i04_md80_100.jpg)

**Notação resumida**

Notação compacta, útil para discussões sobre a estrutura geral do banco de dados, utilizada quando não se deseja entrar em um nível maior de detalhamento.

Para simplificar a representação da modelagem relacional, podemos utilizar o esquema resumido da seguinte maneira:

1. Escrever o nome da entidade e, entre parênteses, todos os atributos, chave primária e chaves estrangeiras (se houver).
2. Sublinhar a chave primária.
3. Na linha abaixo à da entidade devem ser referenciadas todas as chaves estrangeiras e a entidade com as quais se relacionam.

O exemplo apresentado anteriormente poderia ser representado utilizando-se a notação resumida da seguinte forma:

**Departamento (****CodDept****, Nome)**

**Funcionario (****CodFunc****, Nome, CPF, CodDept)**

**CodDept referencia Departamento**

O relacionamento entre as tabelas **Departamento** e **Funcionario** também pode ser representado por meio do seguinte diagrama:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121838/a08i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121838/a08i05_md80_100.jpg)

Observe que por meio da notação resumida não é possível determinar se o relacionamento é do tipo 1:1 ou 1:N (como no caso representado na figura acima).

**Chave alternativa**

É aquela chave que poderia, por causa de suas características, ser chave primária, mas não é. Ela é única na entidade, assim como a chave primária, e pode ser considerada uma chave secundária.

Podemos considerar chave alternativa o CPF. No mundo real, é o que identifica qualquer pessoa física.

**Escolha da chave primária**

Geralmente, a chave primária é um número criado pela aplicação – costuma-se utilizar um recurso de numeração automática do próprio banco de dados, de modo que o número não se repita.

Se a chave primária é muito grande, está sujeita a erros de digitação.

Um nome de pessoa pode ser considerado uma chave primária? O maior problema do nome é que duas ou mais pessoas podem apresentar o mesmo nome (homônimos) e a chave deve ser única para cada registro de dados.

As pessoas podem ter os mesmos nome e sobrenome, mas o RG e CPF são diferentes, entretanto, são números muito grandes, por isso, é costume escolher outros identificadores como chaves primárias.

**Integridade de dados**

Impor a integridade de dados garante a qualidade destes em um banco de dados. Eles devem refletir corretamente a realidade representada pelo banco e também devem ser consistentes entre si. A integridade de dados deve ser implementada de diversas formas em um banco de dados.

- **Integridade de domínio**

Zela pelos valores ideais e necessários para um atributo. Para isso, definimos algumas regras de validação por meio de expressões compostas de valores constantes. Exemplos:

- Não permitir um estoque negativo.
- Impedir uma data de nascimento superior à data atual.
- Não permitir que o valor de um produto seja negativo.
- **Integridade de entidade**

Tem o objetivo de validar os valores permitidos a partir de valores já inseridos na própria entidade. Após uma "autoconsulta" a entidade vai permitir ou não a gravação do novo registro. Exemplos:

- Não permitir duas pessoas com o mesmo CPF.
- Impedir a locação de uma fita que já está locada.
- **Integridade referencial**

Zela pela consistência dos registros de uma entidade a partir de valores provenientes de outras entidades, isto é, determinado registro vai "depender" diretamente de um registro de outra tabela. Exemplos:

- Um registro em uma tabela pai pode ter um ou mais registros em uma tabela filho.
- Um registro em uma tabela filho sempre tem um registro coincidente em uma tabela pai.
- Para a inclusão de um registro em uma determinada tabela filho, é necessário que exista um registro pai coincidente.
- Um registro pai só poderá ser excluído se não possuir nenhum registro filho.