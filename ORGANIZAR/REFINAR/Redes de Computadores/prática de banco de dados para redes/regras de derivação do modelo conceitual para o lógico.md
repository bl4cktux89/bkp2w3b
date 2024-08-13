**Introdução**

A construção de um modelo não é tarefa a ser executada uma única vez. Gradativamente, são acrescentados novos conceitos aos já existentes, aperfeiçoando o modelo.

Na prática, observa-se que nenhuma das estratégias propostas na literatura é universalmente aceita. Normalmente, é aplicada uma construção das diversas estratégias de modelagem (HEUSER, 1999).

A modelagem pode surgir da descrição de dados já existentes ou a partir do conhecimento do mundo real relatado pelas pessoas envolvidas.

No caso de a modelagem estar baseada em dados já existentes, é utilizada a engenharia reversa.

A engenharia reversa utiliza a estratégia **botton-up** (de baixo para cima), ou seja, inicia a modelagem a partir das tabelas de dados já formatados no mundo real e adapta-os, segundo as regras de normalização, até chegar ao modelo conceitual.

Quando a modelagem é feita por meio de uma análise de requisitos, em que a descrição do mundo real é elaborada a partir daquilo que as pessoas conhecem a respeito da realidade a ser moldada, podem ser adotadas duas estratégias: **top-down** (de cima para baixo) ou **inside-up** (de dentro para fora) (HEISER,1999).

**Top-down**

Partindo de uma análise de requisitos, é possível identificar as entidades envolvidas do mundo real e criar o primeiro modelo conceitual, definindo os relacionamentos e a cardinalidade máxima.

Em uma próxima etapa, colocam-se as cardinalidades mínimas e atributos e desmembram-se as entidades associativas dos relacionamentos de N:N.

Em seguida, realiza-se um teste de validação dos modelos, a partir de dados fictícios, simulando a realidade. O usuário deve participar deste teste.

**Inside-up**

Parte de uma ideia central em que são definidas as principais entidades que se relacionam no mundo real e, em seguida, são desenhadas no centro do modelo. A partir dele, desenha-se o detalhamento, ampliando os relacionamentos, assim como no modelo top-down.

Na primeira etapa, desenha-se o modelo conceitual com os relacionamentos e a cardinalidade máxima, a generalização e especialização e os relacionamentos ternários.

Na segunda, inserem-se os novos relacionamentos que surgem da ideia central e acrescenta-se as entidades associadas aos relacionamentos de N:N. Em seguida, coloca-se todos os atributos comuns.

A terceira etapa é o teste de validação, assim como no top-down.

**Modelagem relacional**

A modelagem relacional é a representação do modelo conceitual em forma de tabela, com seus atributos, contendo dados fictícios que simulam a parte do mundo real a ser modelada.

Tomando como exemplo o modelo conceitual do consultório médico, temos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121851/a09i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121851/a09i01_md80_100.jpg)

Passando para o modelo lógico (relacional) teremos o seguinte diagrama:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121852/a09i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121852/a09i02_md80_100.jpg)

**PK** – Representa a chave primária.

**FK** – Representa a chave estrangeira.

Podemos utilizar a notação resumida (também chamada de esquema resumido) para representar a mesma situação:

**Medico (****CRM****, Nome)**

**Paciente (****ID_Paciente****, Nome)**

**Consulta (****CRM, IdPaciente, Data, Hora****)**

**CRM referencia Medico**

**Id_Paciente referencia Paciente**

As tabelas a seguir estão representadas com exemplos de dados. É possível notar que elas foram preenchidas com suas chaves primárias e as chaves estrangeiras correspondentes da tabela relacionada.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121853/a09i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121853/a09i03_md80_100.jpg)