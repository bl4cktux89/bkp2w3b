[![](https://ampli-images.s3.amazonaws.com/production/c01aaae8-9b65-4161-a8d2-1fb81848b314/original)](https://ampli-images.s3.amazonaws.com/production/c01aaae8-9b65-4161-a8d2-1fb81848b314/original)

O modelo lógico do banco de dados é a etapa em que mapeamos o conceito de modelos de entidade e relacionamentos com o foco na criação do banco de dados. Nessa etapa, as entidades são transformadas em tabelas para armazenar as informações, os relacionamentos são estabelecidos, as regras são e os de tipos de dados para cada campo da tabela são determinados (KORTH; SILBERSCHATZ; SUDARSHAN, 2012). O modelo lógico se transforma de um modelo mais abstrato (conceitual) para um modelo com mais detalhes de implementação, ou seja, mais próximo do que será de fato implementado. Cougo (1997) define como modelo lógico de dados aquele em que os objetos, suas características e seus relacionamentos sejam representados de acordo com as regras de implementação e com os limites impostos por alguma tecnologia de determinado SGBD. No modelo lógico serão determinados os relacionamentos e as chaves entre as tabelas, assunto que abordaremos na aula 2. Além da forma gráfica, podemos utilizar a forma textual (Figura abaixo), que ajuda a detalhar os atributos da tabela, deixando a forma gráfica mais “limpa”, somente com a figura e com os seus respectivos nomes das tabelas.

[![](https://ampli-images.s3.amazonaws.com/production/71c112a7-1b2e-4e27-a480-4234f6a1ff09/original)](https://ampli-images.s3.amazonaws.com/production/71c112a7-1b2e-4e27-a480-4234f6a1ff09/original)

Forma Gráfica e Textual.

**🔁 Assimile**

No modelo da Figura acima, é criado um campo chave chamado código. Observe que foi utilizado o sinal # para determinar que esse atributo é diferente dos demais e que possui um papel importante, conforme veremos mais adiante.

_______

Uma boa prática de desenvolvimento de banco de dados é um modelo lógico de dados ser criado a partir do modelo conceitual. Contudo, o modelo lógico pode ser construído diretamente, sem o modelo conceitual, a desvantagem é que a participação do usuário pode ficar comprometida e a possibilidade de erros é grande no ambiente de negócios da empresa.

Na última fase do projeto de banco de dados é realizada a modelagem física. Navathe e Ramez (2005) afirmam que é justamente nesta fase que são determinadas as estruturas de armazenamento interno, as chaves (ou índices) e os diversos caminhos de acessos a base de dados. Paralelamente às atividades de modelagem física, são criados os _softwares_ de aplicação que irão interagir com o banco de dados implementado. Nessa fase, as regras de cada SGBD devem ser utilizadas e as regras de segurança devem ser implementadas, tais como as políticas de _backup_ e as permissões de acessos de cada usuário do banco de dados.

Korth, Silberschatz e Sudarshan (2012) descrevem que, na modelagem física, é utilizada a linguagem _Structured Query Language_ ou Linguagem de Consulta Estruturada (SQL), que tem como principal objetivo a manipulação dos bancos de dados relacionais e é utilizada para interagir com o usuário e com o SGBD, permitindo inserir, consultar, gerenciar, controlar transações, entre outras opções.

Cougo (1997) enfatiza que durante essa fase são utilizadas ferramentas CASE, que auxiliam nas tarefas do desenvolvimento de _software_, desde a análise de requisitos e modelagem, até a programação e os testes na elaboração dos modelos, levando-se sempre em conta o SGBD que será utilizado.

_______

**🔁 Assimile**

Software de aplicação são conjuntos de programas de computador com os quais o usuário pode realizar determinadas tarefas. Por exemplo: o software acadêmico que a secretaria utiliza é o software de aplicação e este _software_ acessa o banco de dados, criados em um SGBD.

_______

Para exemplificar um projeto de banco de dados, vejamos o seguinte estudo de caso como demonstração da diferença entre os modelos conceitual e lógico: uma escola de ensino fundamental bilíngue necessita de um _software_ para seu gerenciamento acadêmico. Após algumas entrevistas, o analista de sistemas levantou os seguintes requisitos essenciais para o projeto de banco de dados:

- A escola possui diversos departamentos, divididos entre as grandes áreas de conhecimento: matemática, estudo da linguagem etc.
- Um departamento pode oferecer diversas disciplinas, mas uma disciplina pertence a somente um departamento.
- Um aluno somente pode estar matriculado em um único curso.
- Uma mesma disciplina pode constar no currículo de diversos cursos.
- Todo professor pertence a um departamento e poderá lecionar em diversas disciplinas.

O analista de sistemas também fez um levantamento sobre quais informações são essenciais e deverão estar armazenadas nas entidades, gerando os seguintes atributos:

- Professores: código, nome, formação, endereço, telefone.
- Curso: código, nome, sigla.
- Disciplinas: código, denominação, sigla, ementa.
- Departamentos: código, denominação.
- Aluno: matrícula, nome, endereço, telefone, filiação e data de nascimento.

Conforme os requisitos determinados pelo cliente, foi elaborado um modelo conceitual simplificado para uma apresentação (Figura abaixo), lembrando que o objetivo é mostrar a estrutura macro do banco de dados.

[![](https://ampli-images.s3.amazonaws.com/production/53bdc9ec-854a-40e7-b56f-973cb025600e/original)](https://ampli-images.s3.amazonaws.com/production/53bdc9ec-854a-40e7-b56f-973cb025600e/original)

Modelo Lógico de uma Escola. Fonte: elaborada pela autora.

O modelo lógico do estudo de caso pode ser analisado na Figura abaixo. Observe que novas entidades apareceram: currículo e prof-disc (nas próximas aulas o surgimento destas entidades ficará mais compreensível). Para a criação do modelo lógico, que foi simplificado para fins didáticos, foi utilizado o SGBD Access®, pela sua facilidade de compreensão.

[![](https://ampli-images.s3.amazonaws.com/production/ee2abd09-e33a-4620-af09-d7f201c947aa/original)](https://ampli-images.s3.amazonaws.com/production/ee2abd09-e33a-4620-af09-d7f201c947aa/original)

Modelo Lógico em um SGBD. Fonte: captura de tela no Microsoft Access, elaborada pela autora.

**💭 Reflita**

O modelo lógico é sempre mais complexo que o modelo conceitual. Observando as figuras acima, onde o boletim de cada aluno se encaixaria? E o diário do professor, de que forma poderia ser representado? A formação do professor não poderia ser uma tabela?

_______

A última etapa, o modelo físico, dependerá do SGBD a ser utilizado. E, somente para termos uma ideia dos comandos SQL utilizados nesta etapa, observe a figura abaixo que tem a finalidade de criar uma tabela, no caso, a tabela Departamento.

[![](https://ampli-images.s3.amazonaws.com/production/a8baa26c-a9a4-4024-b36d-6e0d02cb3108/original)](https://ampli-images.s3.amazonaws.com/production/a8baa26c-a9a4-4024-b36d-6e0d02cb3108/original)

Exemplo comando SQL. Fonte: elaborada pela autora.

**➕ Pesquise mais**

SQL é uma linguagem muito utilizada no banco de dados pelo DBA e por usuários mais capacitados na empresa. Conheça mais sobre SQL e conheça os seus comandos básicos.

EDSON PIMENTEL. [Sql](https://www.youtube.com/watch?v=FHflxAyQlt8) – DDL – Introdução. 29 nov. 2009.