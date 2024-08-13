[![](https://ampli-images.s3.amazonaws.com/production/b9c81423-526a-4b53-bd60-d78120d99d2c/original)](https://ampli-images.s3.amazonaws.com/production/b9c81423-526a-4b53-bd60-d78120d99d2c/original)

A modelagem de uma base de dados precisa obedecer a certos princípios técnicos. Vale ressaltar que a modelagem é reflexo da experiência de cada analista de sistemas ou programador. Após a realização de vários softwares, o profissional da área de TI consegue visualizar os diagramas mentalmente e vai aperfeiçoando-os com auxílio das técnicas de modelagem de dados. O ponto de vista da modelagem é outro fator a ser considerado, e um exemplo seria o sistema de uma padaria. Basicamente, sabemos como funciona uma padaria, mas precisamos saber que cada empresa possui seus padrões e procedimentos que podem influenciar diretamente no processo de modelagem de um banco de dados.

_______

**🔁 Assimile**

A expressão base de dados está relacionada a uma coleção de informações. Podemos afirmar que uma base de dados são os dados armazenados em um banco de dados.

_______

O modelo de dados relacional foi proposto na década de 70 por Peter P. Chen e, desde então, é utilizado para a modelagem de dados, de acordo com Date (2003). Com o passar dos anos, foi aperfeiçoado, porém seu princípio básico ainda é o mesmo. Esse modelo foi baseado na teoria de conjuntos da álgebra relacional. Um banco de dados pode ser representado por um modelo relacional, baseado em uma coleção de relações entre seus integrantes.

Segundo Cougo (1997), um modelo é a representação abstrata e simplificada de um sistema real, gerando um modelo gráfico. Conforme Guimarães (2003), essa forma gráfica (resultante da modelagem relacional) teve grande aceitação por ser um meio de comunicação do projeto conceitual de fácil compreensão por usuários finais de banco de dados. Ao apresentar a modelagem para clientes leigos na área de informática, através dos diagramas, os usuários podem facilmente compreender e ajudar a encontrar problemas na modelagem. Observe a Figura abaixo, em que, mesmo sem saber os conceitos de entidades e relacionamentos, podemos facilmente identificar uma relação entre empregado e cargos e o histórico que é o resultado de vários cargos ocupados por um empregado em alguma empresa. Por ora, não nos concentremos nos diagramas, conforme avançarmos no processo de modelagem, dedicaremos uma aula inteira para esse importante tema.

[![](https://ampli-images.s3.amazonaws.com/production/e538b679-dbdf-457d-8171-a680fdf8c603/original)](https://ampli-images.s3.amazonaws.com/production/e538b679-dbdf-457d-8171-a680fdf8c603/original)

Exemplo modelo relacional. Fonte: elaborada pela autora.

Date (2003) afirma que o modelo relacional não é algo estático, ele evolui e se expande, assim como a própria matemática. A proposta do modelo relacional baseia-se na ideia de que as informações em uma base de dados podem ser representadas em tabelas cujas linhas apresentam as informações cadastradas. A teoria dos conjuntos se aplica no modelo relacional, pois as operações realizadas nas tabelas são baseadas na álgebra relacional, como seleção, união, junção, subtração, produto cartesiano e projeção.

[![](https://ampli-images.s3.amazonaws.com/production/0f0ef551-fa60-448a-a64d-d34d0f86bb1a/original)](https://ampli-images.s3.amazonaws.com/production/0f0ef551-fa60-448a-a64d-d34d0f86bb1a/original)

Exemplo tabela aluno. Fonte: elaborada pela autora.

Conforme Korth, Silberschatz e Sudarshan (2012), o modelo relacional usa um conjunto de tabelas (ou entidades) para representar tanto os dados como as relações entre eles. Na Tabela acima, foram armazenadas quatro informações na tabela Aluno: matrícula, nome, data de nascimento (abreviado: Dt Nasc) e o Curso em que o aluno está matriculado. Neste primeiro momento, analisaremos a disposição das informações: encontram-se em colunas (observe que cada coluna contém uma categoria de informação) e em linhas (observe que em cada linha há informações de um determinado aluno).

Um modelo relacional é composto de muitas tabelas. Date (2003) descreve o modelo relacional como tendo três aspectos básicos:

- **Estrutural**: os dados inseridos no banco de dados são reconhecidos pelos usuários como tabelas.
- **De integridade**: as tabelas precisam satisfazer as restrições de integridades (será abordado na próxima unidade).
- **Manipulador**: são as operações que poderemos realizar com as tabelas, com a intenção de juntar, selecionar, excluir, entre outras operações.

A Tabela acima representa a estrutura de uma tabela com informações sobre alunos. Podemos afirmar, com certeza, que haveria muito mais informações para serem armazenadas. O ideal é criar a estrutura da tabela com o máximo de precisão, mas os SGBDs atuais permitem, com até certa facilidade, adicionar novas informações nas tabelas.

_______

**💭 Reflita**

Quais seriam as vantagens do modelo relacional de banco de dados? Por que após tantos anos de sua criação ainda é um dos procedimentos mais utilizados no desenvolvimento de sistemas?