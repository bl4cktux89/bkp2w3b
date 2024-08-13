[![](https://ampli-images.s3.amazonaws.com/production/3daa7de0-2916-451e-820c-abd8da53c838/original)](https://ampli-images.s3.amazonaws.com/production/3daa7de0-2916-451e-820c-abd8da53c838/original)

No desenvolvimento de qualquer software devemos sempre considerar o seu ciclo de vida, que nada mais é do que o início do software através do estudo e do planejamento de sua viabilidade até o seu término na fase da manutenção ou do abandono do software. Em um projeto de banco de dados também há um ciclo de vida que determinará o começo do projeto até o seu final (que neste caso é a manutenção ou a evolução do banco de dados). Coronel e Rob (2011) destacam as seis fases e suas respectivas ações do ciclo de vida de um banco de dados:

- Estudo inicial do banco de dados: estudo dos requisitos do problema e suas restrições e definição dos objetivos, escopo e fronteiras do banco de dados.
- Projeto do banco de dados: criação do projeto conceitual, escolha do sistema de gerenciamento do banco de dados (SGBD) que deverá ser usado e criação do projeto lógico e físico do banco de dados.
- Implementação e carga: instalação do SGBD, criação do banco de dados e carregamento ou conversão dos dados que serão armazenados no banco.
- Teste e avaliação: realização de testes na base de dados para encontrar possíveis erros.
- Operação: o banco entra em funcionamento nos aplicativos desenvolvidos em paralelo.
- Manutenção e evolução: assim que entra em operação, o banco de dados deve sempre receber manutenção para ficar o máximo possível em plena operação e a evolução do banco de dados acontece assim que novas necessidades do usuário surgem.

_______

📝 **Exemplificando**

As manutenções que acontecem em um banco de dados podem ser:

- **Preventiva**: por causa do backup.
- **Corretiva**: se houver necessidade de recuperação de informação.
- **Adaptativa**: para melhorar o desempenho, para acrescentar tabelas ou campos ou para dar permissões de acessos.

_______

Conforme afirmam Coronel e Rob (2011), há duas abordagens clássicas tradicionais que podem ser adotadas como estratégia de modelagem em um diagrama de entidade-relacionamentos:

- **Estratégia** _**top-down**_: inicializa-se identificando os conjuntos de dados e, em seguida, são definidos os elementos de cada um desses conjuntos. O processo envolve a identificação de diferentes tipos de entidades e a definição de cada atributo. Esta técnica é utilizada em banco de dados maiores.
- **Estratégia** _**bottom-up**_: primeiramente são identificados os elementos de dados, ou seja, os itens, e então eles são agrupados em conjuntos de dados. Neste caso, os atributos são identificados primeiro e, ao agrupá-los, teremos as tabelas. Geralmente, esta técnica é utilizada em banco de dados pequenos.

As abordagens _top-down_ e _bottom-up_ acabam se complementando, pois muitas vezes um analista ou projetista aplica as duas técnicas no mesmo banco de dados a ser modelado, surgindo então uma abordagem mista, denominada _middle-up-down_.

A modelagem conceitual em um projeto de banco de dados   é considerada de alto nível, pois possui como finalidade a fácil compreensão entre os usuários envolvidos na modelagem,  como ressaltam Korth, Silberschatz e Sudarshan (2012). O foco da modelagem conceitual (Quadro abaixo) é detalhar e discutir o funcionamento do negócio do cliente e não o uso de determinada tecnologia, descartando dados de como as informações serão armazenadas e depois recuperadas em banco de dados.

[![](https://ampli-images.s3.amazonaws.com/production/a22873b3-87a1-44fa-874e-1f8c97c94612/original)](https://ampli-images.s3.amazonaws.com/production/a22873b3-87a1-44fa-874e-1f8c97c94612/original)

Comparação entre as modelagens conceitual e lógica. Fonte: elaborado pela autora.

Assim que o modelo lógico começar a ser implementado, o modelo conceitual servirá de apoio à construção do esquema do banco de dados. Navathe e Ramez (2005) afirmam que durante ou mesmo ao término do esquema conceitual, as operações básicas do modelo de dados podem ser usadas para especificar as operações de alto nível do usuário e servem para verificar se o modelo possui todos os requisitos listados pelo cliente.

Para criar um modelo lógico e mais coeso do banco de dados, são necessárias várias revisões na descrição do modelo conceitual (de alto nível) e, desta forma, encontrar:

- Tabelas: em substantivos, objetos reais e objetos que podem armazenar informações.

Assim que o modelo lógico começar a ser implementado, o modelo conceitual servirá de apoio à construção do esquema do banco de dados. Navathe e Ramez (2005) afirmam que durante ou mesmo ao término do esquema conceitual, as operações básicas do modelo de dados podem ser usadas para especificar as operações de alto nível do usuário e servem para verificar se o modelo possui todos os requisitos listados pelo cliente.

Para criar um modelo lógico e mais coeso do banco de dados, são necessárias várias revisões na descrição do modelo conceitual (de alto nível) e, desta forma, encontrar:

- **Tabelas**: em substantivos, objetos reais e objetos que podem armazenar informações.
- **Campos**: em características específicas de algum objeto ou adjetivos.
- **Relacionamentos**: em verbos que “ligam” uma tabela a outra.
- **Cardinalidades**: a quantidade de vezes que cada tabela pode estar relacionada com outra.

Algumas normas precisam ser adotadas durante a criação do modelo lógico do banco de dados, na criação do diagrama de entidade-relacionamentos. Estão elencadas abaixo as principais regras que norteiam os fundamentos da modelagem de dados, conforme adaptado de Heuser (2011):

- Em casos de relacionamento 1 para N: a chave primária do lado 1 sempre deverá estar na tabela do lado N como uma chave estrangeira.
- Em casos de relacionamento N para N: o relacionamento passa a ser implementado como tabela própria que possui campos específicos relacionados entre as duas tabelas que deram origem a esta nova tabela, chamada tabela associativa.

_______

**🔁 Assimile**

As tabelas devem ter o número reduzido de chaves primárias ao mínimo possível, ou seja, sempre que possível, uma tabela deverá ter somente um identificador único, evitando chaves alternativas.

_______

Na maioria dos projetos existe uma grande quantidade de tabelas e campos envolvidos. É necessário criar padrões de desenvolvimento para evitar problemas de conflito de nomes de atributos, por exemplo. Em uma modelagem em que dois ou três analistas ou programadores estejam trabalhando, caso não haja um padrão, o mesmo campo pode ser criado e referenciado  com nomes diferentes, dificultando uma consulta ou alguma manutenção realizada posteriormente. É necessário criar o dicionário de dados para estabelecer uma padronização e uma documentação sobre cada tabela criada. Korth, Silberschatz e Sudarshan (2012) mencionam um dicionário como uma descrição de dados, ou seja, contém _metadados_ que são detalhes dos dados armazenados na tabela. Observe no Quadro abaixo um exemplo simplificado de dicionário de dados.

[![](https://ampli-images.s3.amazonaws.com/production/8a429919-8b02-4aa8-9269-54f6118efb31/original)](https://ampli-images.s3.amazonaws.com/production/8a429919-8b02-4aa8-9269-54f6118efb31/original)

Dicionário de dados da tabela funcionários. Fonte: elaborado pela autora.