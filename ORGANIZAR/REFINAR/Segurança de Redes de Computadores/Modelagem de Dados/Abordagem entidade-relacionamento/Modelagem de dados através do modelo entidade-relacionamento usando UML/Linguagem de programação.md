[![](https://ampli-images.s3.amazonaws.com/production/1c4cc65f-046a-4ca7-b790-c97e007914ba/original)](https://ampli-images.s3.amazonaws.com/production/1c4cc65f-046a-4ca7-b790-c97e007914ba/original)

Atualmente, a maioria das linguagens de programação é orientada a objetos, entre elas, podemos citar Java e C# que, apesar de serem diferentes, compartilham dos mesmos conceitos e paradigmas da programação orientada a objetos. Um software desenvolvido nestas linguagens utilizando classes pode perfeitamente armazenar as informações em bases de dados relacionais. Porém, antes de mais nada, o que é um objeto? Um objeto pode ser uma pessoa, alguma coisa, um processo real ou abstrato e que possua informações e funcionalidades, podendo representar:

- **Entidades físicas**: um cliente, uma bicicleta, um imóvel.
- **Entidade conceitual**: um diagrama entidade-relacionamentos de um sistema.
- **Entidade de software**: um botão de confirmação de um software.

Podemos agrupar as informações comuns de um objeto, surgindo então a classe, que pode ser classificada como uma entidade teórica usada para modelar um objeto. A classe deve ser exclusivamente criada para guardar informações de um determinado objeto. A Figura abaixo demonstra o exemplo do objeto Carro, que tem as suas informações armazenadas em uma classe Carro.

[![](https://ampli-images.s3.amazonaws.com/production/02d1e197-a99d-4cd9-9362-a68613d3ef22/original)](https://ampli-images.s3.amazonaws.com/production/02d1e197-a99d-4cd9-9362-a68613d3ef22/original)

Exemplo da classe carro. Fonte: elaborada pela autora.

Uma classe é dividida em três partes: o nome, os atributos e os seus métodos, como na Figura abaixo. O nome deve ser referente ao que a classe representa, isto é, ao ler o nome da classe, já devemos identificar o que ela vai armazenar. Os atributos são as características do objeto. Os métodos são os comportamentos que um objeto poderá assumir. Fazendo uma analogia à linguagem de programação C++, os métodos são as funções criadas para realizar alguma tarefa referente aos seus atributos ou ao objeto.

[![](https://ampli-images.s3.amazonaws.com/production/f35aa4de-36fc-4168-be58-57aef3817f5a/original)](https://ampli-images.s3.amazonaws.com/production/f35aa4de-36fc-4168-be58-57aef3817f5a/original)

Classe carro. Fonte: elaborado pela autora.

Conforme Mizrahi (2008), uma classe pode ser conceituada como um tipo de dado, assim como os tipos predefinidos que existem em compiladores de diversas linguagens de programação ou do próprio Sistema de Gerenciamento de Banco de Dados (SGBD). Uma classe é formada por dados e comportamentos. Para a definição dos dados de uma classe são utilizados os atributos e, para definir os comportamentos, usamos os métodos (funções que manipulam os atributos da classe). Medeiros (2004) afirma que uma instância de uma classe é a criação de um objeto baseado em uma determinada classe. Ao instanciarmos um objeto, criamos esses objetos na memória.

Você deve estar pensando: “_mas o que isso tem a ver com a modelagem de dados_?”. A resposta é que os objetos serão persistidos em algum banco de dados e, por isso, também precisam ser modelados de acordo com tais regras que estamos aprendendo. Para auxiliar nesse processo de modelagem de classes, existe a Linguagem de Modelagem Unificada ou, como mais utilizada,  a sigla UML (_Unified Modeling Language_), uma ferramenta que auxilia na modelagem de sistemas orientados a objetos. A finalidade da UML é proporcionar uma padronização nos projetos de sistemas, abrangendo aspectos conceituais, como regras de negócios, e artefatos concretos, como as classes, escritas em linguagens de programação, esquemas de banco de dados e componentes de software reutilizáveis, segundo Medeiros (2004).

A Linguagem UML, conforme Fowler (2004), é composta por diversos diagramas, destacando-se os seguintes:

- **Diagrama de classes**: é o mais usado da Linguagem UML, pois pode representar um conjunto de classes e seus relacionamentos.
- **Diagrama de objetos**: demonstra como na realidade as informações do objeto podem ficar armazenadas na classe.
- **Diagrama de caso de uso**: é um complemento do diagrama de classes, utilizado principalmente na fase de especificação dos requisitos do sistema, pois demonstra os usuários e as funcionalidades do software.
- **Diagrama de sequência**: demonstra uma visão ou perspectiva, norteada por tempo, da colaboração entre os objetos, principalmente com a ordem temporal em que as mensagens são trocadas.
- **Diagrama de atividades**: determina o fluxo de tarefas que podem ser executadas pelo software ou por um ator.
- **Diagrama de estados**: pode representar um conjunto de estados que um objeto pode ter e os “gatilhos” que possam estimular a mudança ou a transição do objeto de um estado para outro.
- **Diagrama de componentes**: demonstra os componentes do software e seus relacionamentos, podendo ser: bibliotecas, arquivos de ajuda e classes que podem ser anexadas ao software.

A cardinalidade utilizada em um diagrama de classe é semelhante ao diagrama de entidade-relacionamentos, porém, podemos determinar o número exato de ocorrências, por exemplo, no mínimo 1 ocorrência e no máximo 5. No diagrama DER usamos a letra _N_ para representar “muitos”, já no diagrama de classes é utilizado o sinal de asterisco (*) para a mesma função. Observe que a classe “Estado” na Figura abaixo possui dois atributos do tipo _string_ e um método. Já a classe “Cidade” possui três atributos, sendo dois do tipo inteiro e um do tipo _string_, além de um método. É importante ressaltar que   a quantidade de atributos e métodos varia de projeto para projeto, pois o desenvolvedor deverá modelar a classe da forma que achar mais adequada.

[![](https://ampli-images.s3.amazonaws.com/production/46442332-a98d-464b-aebb-e709f9853725/original)](https://ampli-images.s3.amazonaws.com/production/46442332-a98d-464b-aebb-e709f9853725/original)

Exemplo de relacionamento entre duas classes. Fonte: elaborada pela autora.

Quando uma classe é instanciada  (ação  de  criá-la),  tem-se  um objeto na memória de trabalho do computador. Nesse caso,  os atributos da classe são “preenchidos” com dados. Assim como existe o diagrama de classes, também existe o diagrama de objetos para mostrar as informações que serão armazenadas na classe. A Figura abaixo apresenta um exemplo de como ficarão os atributos apresentados no diagrama da Figura acima.

[![](https://ampli-images.s3.amazonaws.com/production/30bb94df-c693-498a-86fe-d0c1f96c65d2/original)](https://ampli-images.s3.amazonaws.com/production/30bb94df-c693-498a-86fe-d0c1f96c65d2/original)

Exemplo de diagrama de objetos. Fonte: elaborada pela autora.

**🔁 Assimile**

A UML originalmente foi proposta para realizar a modelagem de sistemas orientados a objetos, mas ela pode ser utilizada como uma notação em projetos de banco de dados, deixando a modelagem de todo o sistema de forma padronizada. O diagrama de classes, como visto na Figura acima, pode ser usado para representar o projeto lógico de um banco de dados (geralmente, o modelo conceitual é realizado com o diagrama de entidade-relacionamentos).

_______

Uma classe, quando instanciada, guarda as informações na memória RAM do computador. Toda vez que ela precisa armazenar suas informações para depois recuperá-las, é necessário gravar em arquivos ou em banco de dados. Este processo é chamado de persistência. Uma classe de persistência tem como finalidade guardar as informações em um meio persistente, para que possam ser recuperadas posteriormente.

_______

**📝 Exemplificando**

A persistência de objetos pode ser definida como a capacidade que uma linguagem de programação tem de permitir que os dados e objetos resistam a um processo, para mais tarde utilizá-los em outro. Existem várias técnicas de persistência, como: Padrão DAO (_Data Access Object_), Força Bruta, Active Record, Persistência Robusta (_Framework_) e Padrão JDO (_Java Data Object_).