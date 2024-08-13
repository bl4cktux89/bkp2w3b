[![](https://ampli-images.s3.amazonaws.com/production/26d56a1e-dee1-4cc0-9fbb-56fe1356bacf/original)](https://ampli-images.s3.amazonaws.com/production/26d56a1e-dee1-4cc0-9fbb-56fe1356bacf/original)

Mizrahi (2008) afirma que na programação orientada a objetos podemos relacionar classes com outras classes através de hierarquias. Uma subclasse pode herdar as características de outra classe (neste caso, seria a classe mãe ou superclasse). Na estrutura de herança, as classes compartilham suas funções e características comuns, e as subclasses podem receber outras particularidades exclusivas. A Figura abaixo mostra uma estrutura de herança entre as classes.

[![](https://ampli-images.s3.amazonaws.com/production/b3e67f08-dd62-45eb-81a9-eb923a7e7902/original)](https://ampli-images.s3.amazonaws.com/production/b3e67f08-dd62-45eb-81a9-eb923a7e7902/original)

Exemplo de herança. Fonte: elaborada pela autora

Na Figura acima, a classe Médico é a superclasse e suas duas classes filhas (Cardiologista e Anestesista) herdam os atributos e métodos da classe mãe. Isso significa que os atributos CRM, nome, CPF e dtnasc não precisam ser escritos nas classes filhas, pois serão herdados da superclasse. A classe Anestesista não possui nenhum atributo ou método além dos herdados, porque podemos definir os atributos e métodos conforme necessário (mas precisamos criar a classe no diagrama).

_______

**➕ Pesquise mais**

Saiba mais sobre a modelagem de dados utilizando o UML. Este artigo apresenta uma modelagem de uma aplicação web, demonstrando como as classes persistentes definidas na UML podem ser traduzidas no modelo relacional de um banco de dados.

TANAKA, S. A. et al. [Modelagem de uma aplicação web a partir de  um](http://periodicos.unesc.net/sulcomp/article/viewFile/758/716) [_framework_](http://periodicos.unesc.net/sulcomp/article/viewFile/758/716) [de agenda de tarefas](http://periodicos.unesc.net/sulcomp/article/viewFile/758/716). Londrina, [s.d.].

_______

Estabelecer a herança entre classes é um recurso da orientação a objetos que pode ser empregado na modelagem de dados relacionais, a fim de permitir um melhor suporte a relacionamentos entre estruturas de classes (mãe e filhas).

A herança tem como principal fundamento a possibilidade de criar subclasses que possam herdar características da classe mãe. Esta mesma analogia é aplicada aos modelos de entidade-relacionamentos e, a este processo, em que várias entidades (tabelas) são agrupadas em uma única entidade genérica, damos o nome de generalização. Especialização é o processo inverso, em que novas entidades são criadas com atributos que acrescentam detalhes à entidade genérica.

Korth, Silberschatz e Sudarshan (2012) afirmam que em diagrama de entidade-relacionamentos, a generalização e a especialização são um tipo de relacionamento entre entidades que determina que uma entidade contém a outra, isto quer dizer que uma entidade superior contém um ou mais conjuntos de entidades inferiores.

Cougo (1998) destaca que em um diagrama de entidade- relacionamentos, as estruturas de generalização e especialização são úteis para que sejam retiradas a complexidade de entidades, e o seu uso está diretamente ligado ao nível de detalhamento que desejamos em um modelo lógico. Na Figura abaixo, criamos uma tabela generalizada chamada Funcionário e também as tabelas especializadas chamadas Professor e Secretária. Nesse cenário, as entidades Professor e Secretária possuem atributos da entidade Funcionário, mais as suas específicas.

[![](https://ampli-images.s3.amazonaws.com/production/b96e6a44-4fba-4242-ac9c-f024411d604a/original)](https://ampli-images.s3.amazonaws.com/production/b96e6a44-4fba-4242-ac9c-f024411d604a/original)

Exemplo de generalização-especialização. Fonte: elaborada pela autora.

A estrutura de generalização e especialização é representada pelo triângulo que une as entidades. Quando devemos  usar  estruturas  de generalização e especialização em um diagrama de entidade- relacionamentos? Quando existem atributos (campos das tabelas) específicos para determinada entidade. Uma estrutura de generalização e especialização pode ser classificada em Parcial ou Total. Na Figura abaixo  podemos observar que existe um “p” ao lado do triângulo.

Uma generalização e especialização parcial vista na Figura abaixo, indica que nem todo funcionário é professor ou secretária e, neste caso, não é toda ocorrência da entidade generalizada que possui um entidade especializada correspondente.

[![](https://ampli-images.s3.amazonaws.com/production/b0098893-470b-4d30-ae2e-d37c2bd2af69/original)](https://ampli-images.s3.amazonaws.com/production/b0098893-470b-4d30-ae2e-d37c2bd2af69/original)

Exemplo de generalização e especialização parcial. Fonte: elaborada pela autora.

Podemos ter uma generalização  e  especialização  total  quando, a cada ocorrência da entidade generalizada, houver, obrigatoriamente, a entidade especializada. Na Figura  abaixo  podemos observar um “t” que indica a totalidade e uma seta dupla apontando para a entidade generalizada. Neste exemplo, a seta está indicando que necessariamente um funcionário será ou professor ou secretária.

[![](https://ampli-images.s3.amazonaws.com/production/261aa399-da19-4967-8771-e9c0d9dbaa96/original)](https://ampli-images.s3.amazonaws.com/production/261aa399-da19-4967-8771-e9c0d9dbaa96/original)

Exemplo de generalização e especialização total. Fonte: elaborada pela autora.

**💭 Reflita**

Quais os benefícios da utilização de herança (generalização e especialização) em um diagrama de entidade-relacionamentos? Como podemos detectar essa necessidade em nossos modelos?

_______

Um exemplo prático da  utilização  de  UML  em  um diagrama de entidade-relacionamentos é a aplicação da generalização e especialização, que nada mais é do que usar o conceito de herança no modelo. Digamos que, para uma determinada universidade, precisamos guardar as informações das disciplinas ministradas por professores e as disciplinas que um determinado aluno cursa. Outras informações das tabelas deverão ser armazenadas:

- **Tabela Funcionário**: nome, endereço, RG, CPF, data de nascimento, data de admissão, data de demissão, salário, nome da mãe e nome do pai.
- **Tabela Professor**: nome, endereço, RG, CPF, data de nascimento, nome da mãe, nome do pai, valor da hora da aula e quantidade de horas/aula.
- **Tabela Aluno**: nome, endereço, RG, CPF, data de nascimento, data de entrada faculdade, data de formatura, salário, nome da mãe e nome do pai.

A tabela Disciplina estará relacionada com a tabela Professor e com a tabela Aluno. As tabelas Funcionário, Professor e Aluno têm algo em comum? Algum atributo se repete? Se você leu com atenção, percebeu a repetição dos seguintes atributos: nome, endereço, RG, CPF, data de nascimento, nome da mãe e nome do pai. O que fazer para evitar a repetição? Podemos criar uma entidade chamada Pessoa e nela inserir os atributos repetidos nas demais tabelas. Observe na Figura abaixo, o exemplo de como o modelo conceitual ficará.

[![](https://ampli-images.s3.amazonaws.com/production/ef1e5beb-6377-44ab-8ff0-6e021d94cc17/original)](https://ampli-images.s3.amazonaws.com/production/ef1e5beb-6377-44ab-8ff0-6e021d94cc17/original)

Exemplo do modelo conceitual com generalização e especialização. Fonte: elaborada pela autora.

Korth, Silberschatz e Sudarshan (2012) descrevem que o diagrama de classes pode ser utilizado como ferramenta gráfica para criar o modelo lógico de banco de dados. Observe na Figura abaixo, como ficará o DER com a notação UML.

[![](https://ampli-images.s3.amazonaws.com/production/a9db182e-4b0f-424f-a1ee-4da2b53fb402/original)](https://ampli-images.s3.amazonaws.com/production/a9db182e-4b0f-424f-a1ee-4da2b53fb402/original)

Exemplo do DER com a notação UML. Fonte: elaborada pela autora

**💭 Reflita**

Observando o DER da Figura acima, como você acredita que ficarão as chaves estrangeiras entre as tabelas Aluno e Disciplina – Professor e Disciplina? Como “arrumar” o diagrama e contemplar as chaves estrangeiras?