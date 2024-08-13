[![](https://ampli-images.s3.amazonaws.com/production/18a85839-e982-47f2-9a0b-d583ac415531/original)](https://ampli-images.s3.amazonaws.com/production/18a85839-e982-47f2-9a0b-d583ac415531/original)

Korth, Silberschatz e Sudarshan (2012) enfatizam que uma das principais razões para usarmos os Sistemas Gerenciadores de Banco de Dados é ter um controle central sobre os dados e sobre os programas que os acessam. É necessário que alguém tenha um controle total sobre o sistema, e este usuário é o Administrador do Banco de Dados ou simplesmente DBA (do inglês _Database Management System_). O Administrador do Banco de Dados possui diversas funções que envolvem a instalação, a configuração e a manutenção do SGBD. O DBA também precisa estabelecer regras de acesso aos dados do servidor, monitorar o banco e realizar manutenções preventivas e corretivas.

Entre algumas funções do DBA, segundo Korth, Silberschatz e Sudarshan (2012), destacam-se:

- **Definição do esquema:** é o DBA que cria, modifica e atualiza o esquema do banco de dados, executando um conjunto de instruções.
- **Concessão de autorização ao acesso aos dados**: define quem pode visualizar determinada informação no banco, estabelece juntamente com os administradores da empresa a quais dados cada usuário comum poderá ter acesso.
- **Manutenção de rotina**: liberar espaços no servidor, realizar backup e monitorar as tarefas no servidor (evitando possíveis gargalos de acessos).

É papel do Administrador de Banco de Dados ficar atento às novas tecnologias que surgem. É uma área que requer muito investimento, e os dados de uma empresa são cruciais. Imagine uma empresa multinacional ficar o dia inteiro parada porque o servidor de banco de dados estragou e não havia um esquema de reserva de equipamentos ou de recuperação de backup. É desse profissional a responsabilidade de garantir que a empresa sofra o mínimo possível em caso de problemas de hardware ou de software. É a figura do analista de sistema que geralmente desempenha a função de projetista de banco de dados. Korth, Silberschatz e Sudarshan (2012) afirmam que o projetista de banco de dados precisa interagir extensivamente com especialistas do domínio e usuários para realizar essa tarefa, pois ele é quem criará uma representação gráfica dos requisitos do cliente. Neste livro, trataremos do papel do projetista como função do analista de sistemas.

_______

**🔁 Assimile**

Os usuários dos bancos de dados podem possuir várias formas de acessos sobre os dados e podem ter autorização para: somente leitura, inserir novos dados, atualizar e excluir os dados. Um usuário pode ter um ou mais acessos, sendo que poucas pessoas devem possuir acessos à exclusão de dados.

_______

O modelo relacional usa um conjunto de tabelas para representar os dados como a relação ente eles, cada tabela possui múltiplas colunas e cada uma possui um nome único, como afirmam Korth, Silberschatz e Sudarshan (2012). As tabelas também podem ser denominadas como: entidades, cadastros ou arquivos. Elmasri e Navathe (2005) declaram que as entidades podem representar objetos com existência física, como uma pessoa, um carro, um animal. Podem também representar um objeto com existência conceitual, como um projeto, um departamento, um trabalho acadêmico.

Para Guimarães (2003), uma entidade é um objeto ou indivíduo do mundo real que possui existência própria e cujas características ou propriedades desejamos registrar. Podemos representar graficamente uma tabela usando retângulos ou losangos. A Figura abaixo mostra o exemplo de três entidades: duas estão em um retângulo e uma num losango. A diferença entre essas formas de representação será detalhada com conceitos que aprenderemos em breve. O mais importante, neste momento, é saber que a entidade “Histórico” irá receber os campos que não podem estar nem na entidade Empregado e nem na entidade Cargo, por exemplo: data de início e data de fim da ocupação de determinado cargo pelo empregado.

[![](https://ampli-images.s3.amazonaws.com/production/ece5313a-a593-49b5-a72a-728d91f068b4/original)](https://ampli-images.s3.amazonaws.com/production/ece5313a-a593-49b5-a72a-728d91f068b4/original)

Exemplo de entidades. Fonte: elaborada pela autora.

As entidades possuem características próprias e que podem variar na quantidade conforme a necessidade de cada sistema. Suponha que tenhamos uma entidade chamada Animal. Nesta entidade podemos armazenar várias informações básicas de acordo com a necessidade do sistema a ser realizado. Digamos, por exemplo, que se fosse no sentido de venda do animal, na entidade Animal teríamos as seguintes informações: data de nascimento, sexo, raça, porte e valor de venda. Agora, se o objetivo não fosse para a venda do animal e sim para algum serviço a uma clínica veterinária, as informações armazenadas poderiam ser vacinas tomadas, peso, altura, histórico de doenças e muito mais.

_______

**🔁 Assimile**

A nomenclatura para as entidades e os atributos é padronizada pelas empresas de desenvolvimento de software. As entidades devem estar no singular e começar com letra maiúscula. Já o atributo poderá ser abreviado, por exemplo: nm para nome. Algumas empresas utilizam o nome da entidade atrás do nome do atributo (campo): nm_aluno. No SGBD não é aconselhável utilizar espaços em branco, números ou caracteres especiais como nome de entidades e atributos (mas para efeitos didáticos, iremos usá-los neste livro).

_______

As informações que armazenamos em tabelas podem ser agrupadas e são o que chamamos de atributos, campos ou colunas. Na Tabela abaixo podemos observar que a tabela Aluno possui quatro campos: matrícula, nome, data de nascimento e curso. Cada coluna representa uma categoria de informação, portanto nesta coluna somente será permitido inserir o campo desta categoria, por exemplo, na coluna nome somente o nome do aluno deverá ser digitado. Um conjunto de atributos logicamente dispostos em uma entidade (ou tabela) são conhecidos como registros, linhas ou tuplas. Uma tabela poderá ter milhares de registros. Observe que na tabela possuímos um campo chamado curso, ele está disposto nesta tabela somente como exemplo ilustrativo. Na próxima unidade, veremos que esse campo virá de uma tabela (através do relacionamento), precisamos tomar certos cuidados para evitar que tabelas se escondam em outras tabelas como forma de campos e, este é um dos segredos da modelagem de dados: descobrir essas tabelas escondidas.

[![](https://ampli-images.s3.amazonaws.com/production/e3eb1806-652f-4703-a66e-037ac1f52c8e/original)](https://ampli-images.s3.amazonaws.com/production/e3eb1806-652f-4703-a66e-037ac1f52c8e/original)

Exemplo de campo ou atributo. Fonte: elaborada pela autora.

**📝 Exemplificando**

Os atributos ou campos de uma tabela possuem tipos que devem ser cuidadosamente declarados para evitar desperdício de armazenamento. Por exemplo: o campo nome deverá ser do tipo texto, mas se o campo for quantidade de filhos, o correto é declarar com inteiro (ou byte) e não como texto.

_______

O processo de modelagem de dados visa buscar informações para criar o banco de dados. Saber identificar corretamente uma entidade é um dos primeiros passos para obter sucesso no desenvolvimento do software. Um analista de sistemas ou projetista do banco de dados deve sempre estar atento aos detalhes que uma entidade ou um atributo pode revelar: pode se tornar outras entidades.