[![](https://ampli-images.s3.amazonaws.com/production/41868aaa-6ff8-4567-a1cb-98f17ec1953e/original)](https://ampli-images.s3.amazonaws.com/production/41868aaa-6ff8-4567-a1cb-98f17ec1953e/original)

Quando uma empresa investe na criação de um software, ela espera, além do funcionamento, rapidez nos resultados. As demandas por consultas ao banco de dados sempre são grandes e há constantemente necessidades de novas consultas. Um banco de dados mal projetado pode exigir muito tempo de espera por resultados e o pior poderá acontecer: erros duplicados e imprecisos. A normalização de tabelas, segundo Coronel e Rob (2011), é um método para avaliar e corrigir estruturas de tabelas com o propósito de reduzir as redundâncias de dados, reduzindo dessa forma a possibilidades de erros e anomalias em uma tabela. Para atingir os objetivos da normalização, conforme Coronel e Rob (2011), as tabelas precisam ter as seguintes propriedades:

- Cada tabela deverá tratar de somente um único assunto, por exemplo: uma tabela com informações sobre remédio, não poderá ter informações de um médico.
- O mesmo campo não poderá ser armazenado, desnecessariamente, em mais de uma tabela. Essa é uma garantia de que não será necessária a atualização do mesmo campo, em mais de uma tabela.
- Os campos de uma tabela são dependentes da chave primária dessa tabela e de mais nenhum campo.
- A tabela deverá estar livre de anomalias de inserção, atualização e exclusão, garantindo a integridade e a consistência dos dados, por exemplo: na tabela Cliente será necessário informar a cidade de seu nascimento, não devemos deixar ele informar a cidade, mas escolher a cidade dentre as cidades previamente cadastradas ou por meio de uma busca do CEP (que trará o endereço completo).

Para aplicar as regras da normalização, um dos alvos a ser observado são os campos (ou atributos) que fazem parte das tabelas. Podemos classificar os atributos, conforme Korth, Silberschatz e Sudarshan (2012), de um Modelo EntidadeRelacionamento como:

- **Atributo simples ou atômico**: é o atributo que não é divisível, possui um sentido único, como o RG ou o CPF de uma pessoa, esses dois exemplos mostram que tanto o RG quanto o CPF não podem ser divididos em dois outros campos.
- **Atributo composto**: é um atributo que pode ser divido em várias partes, um bom exemplo é o endereço. Podemos dividir esse atributo em: rua, número, complemento, bairro.
- **Atributo monovalorado**: é um atributo que possui apenas um valor para a tabela, como a matrícula de um aluno, esse número não poderá se repetir na tabela.
- **Atributo multivalorado**: é um atributo que pode receber mais de uma informação, o melhor exemplo é o telefone que pode receber mais de um valor.
- **Atributo derivado**: o valor desse tipo de atributo pode originar de outra tabela ou de outros campos. Digamos que para um cardiologista seja necessário saber a idade (em anos e dias). Podemos calculá-la a partir da data de nascimento e da data de atendimento no ato da consulta médica.
- **Atributo chave**: é o atributo escolhido ou criado para que possa indicar o registro (a linha) da tabela.

A Primeira Forma Normal, ou simplesmente 1FN, possui a seguinte regra: uma tabela estará na Primeira Forma Norma se, e somente se, todos os seus atributos forem atômicos, não possuindo grupos repetitivos ou colunas que possuam mais de um valor. Para estar na 1FN os seguintes passos devem ser realizados:

- Identificar a chave primária da tabela.
- Identificar a coluna que possua dados repetidos.
- Remover a coluna que tenha dados repetidos.
- Criar uma nova tabela para armazenar os dados repetidos.
- Criar um relacionamento entre a tabela que está sendo normalizada e a sua tabela secundária.

No Quadro abaixo, podemos observar a tabela _Funcionário_ que não está normalizada e que possui diversos campos.

[![](https://ampli-images.s3.amazonaws.com/production/545841da-3f02-44c4-a0e4-f413e4d60dde/original)](https://ampli-images.s3.amazonaws.com/production/545841da-3f02-44c4-a0e4-f413e4d60dde/original)

Tabela não normalizada de funcionário. Fonte: elaborado pela autora.

**💭 Reflita**

No Quadro acima a tabela Funcionário não está normalizada. Analisando a tabela, quais os campos que apresentam problemas? Todos os campos realmente pertencem a essa tabela? Existem campos que podem ser chaves estrangeiras e que podem ser representados em outra tabela?

_______

Para deixar a tabela Funcionário na Primeira Forma Normal (1FN) primeiramente devemos verificar: alguns dos campos podem ser a chave primária? Pelo que observamos, é melhor criar um campo novo e indicar como a chave primária. Uma boa sugestão é o campo: matrícula ou código do funcionário, observe como ficará a tabela, no modo textual:

Funcionário: (**\#matrículaFunc**, nome, idade, data de admissão, valor da hora, cidade, departamento).

Podemos melhorar mais alguma coisa? Observe que há os campos: cidade e departamento. Para normalizar a tabela _Funcionário_ para que fique na 1FN, devemos fazer o seguinte:

- **Primeiro**: criar uma tabela chamada Cidade.
- **Segundo**: inserir a chave estrangeira da tabela Cidade na tabela Funcionário.

_______

**📝 Exemplificando**

Observe como ficaram as tabelas após a 1FN sendo aplicada:

Cidade (**\#idCidade**, Cidade)

Funcionários (**\#matrículaFunc**, nome, idade, valordahora, dtadmissão, Departamento, &idCidade)

_______

No Quadro abaixo, observe a tabela Funcionário que agora está na Primeira Forma Normal (1FN).

[![](https://ampli-images.s3.amazonaws.com/production/a415b815-06d4-4d2b-aacc-e3465f5b233f/original)](https://ampli-images.s3.amazonaws.com/production/a415b815-06d4-4d2b-aacc-e3465f5b233f/original)

Tabela Funcionário na 1FN. Fonte: elaborado pela autora.

Verificando mais uma vez os campos da tabela, observe o campo _idade_. Não está errado guardar, porém, a cada mudança de _idade_ de um funcionário, uma atualização deverá ser realizada na tabela. Isso não é nem de longe prático e ideal para um banco de dados. Então, como resolver? Criar o campo _data de nascimento_ em vez do campo _idade_. Agora a tabela ficará da seguinte forma: Funcionários (**\#matrículaFunc**, nome, dtNascimento, valordahora, dtadmissão, Departamento, &idCidade).

_______

**🔁 Assimile**

Para uma tabela estar na Primeira Forma Normal, todos os seus campos ou atributos deverão ser monovalorados e atômicos.