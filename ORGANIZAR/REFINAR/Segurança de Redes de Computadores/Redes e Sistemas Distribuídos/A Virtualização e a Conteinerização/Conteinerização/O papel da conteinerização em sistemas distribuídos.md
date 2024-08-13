[![](https://ampli-images.s3.amazonaws.com/production/0e34d0e9-d09b-4bcb-915f-7431c8dd6458/original)](https://ampli-images.s3.amazonaws.com/production/0e34d0e9-d09b-4bcb-915f-7431c8dd6458/original)

Os sistemas distribuídos fazem uso extensivo dos contêineres no contexto de microsserviços. A ideia dos microsserviços está associada a empresas que possuem sistemas altamente dinâmicos e ao termo modularidade. Um portal de notícias por exemplo, é composto por vários elementos, como um (ou mais) banco de dados, um (ou mais) _framework front-end_ utilizado para desenvolver interfaces, _framework back-end_ para desenvolver a parte dinâmica do sistema, frameworks para gerenciar mensagens entre servidores e clientes (por exemplo, o RabbitMQ) etc.

Caso o sistema possua uma arquitetura monolítica, ou seja, uma forte dependência entre esses elementos, será muito difícil substituir alguns dos elementos citados anteriormente sem causar uma interrupção completa no sistema. Por outro lado, em uma arquitetura baseada em microsserviços, esses componentes têm um baixo acoplamento entre si, ou seja, o grau de dependência entre os componentes é baixo, de forma que, caso você tenha de fazer uma substituição, terá um impacto bem menor na indisponibilidade do seu sistema, e os contêineres serão artefatos fundamentais para atingir esse baixo acoplamento, pois cada um dos elementos pode ser criado e implantado em um contêiner separado.

Dentre as vantagens de um sistema distribuído baseado em microsserviços, podemos apontar que quanto menores são as partes, mais fácil entendê-las. Além disso, cada microsserviço pode ser executado e escalado de maneira concorrente e independente entre si. Outra vantagem decorrente disso é que, como esses elementos possuem um baixo acoplamento entre si, um projeto de grande porte pode ser trabalhado de maneira razoavelmente independente entre as equipes de trabalho. A figura a seguir ilustra uma aplicação monolítica em relação a uma aplicação baseada em microsserviços.

[![](https://ampli-images.s3.amazonaws.com/production/81ad8564-85e8-41cc-882e-e2acc9c01eee/original)](https://ampli-images.s3.amazonaws.com/production/81ad8564-85e8-41cc-882e-e2acc9c01eee/original)

Exemplo de aplicações baseadas em microsserviços. Fonte: elaborada pelo autor.

______

**🔁Assimile**

Atualmente, existe uma grande tendência de empresas migrarem de aplicações monolíticas para aplicações orientadas a microsserviços, por vantagens como escalabilidade e independência entre seus elementos (também conhecido como baixo acoplamento).

______

Como veremos na próxima aula (parte prática), apesar de a criação e o controle de um contêiner ser feita com simples comandos, podemos observar pela figura acima que uma aplicação é composta por não apenas um, mas vários microsserviços, cada um representando um ou mais contêineres. Gerenciar dezenas ou centenas de contêiner, de maneira isolada, pode ser uma tarefa muito trabalhosa, razão pela qual as empresas utilizam alguma ferramenta para criar, gerenciar e remover contêineres.

Esse tipo de ferramenta é conhecido no mercado de trabalho como ferramenta de orquestração de contêineres. Acredita-se que a ideia esteja relacionada ao fato de que, em uma orquestra, um maestro coordena os músicos de maneira que o objetivo conjunto (obra tocada) seja o melhor possível. Nessa analogia, as ferramentas de orquestração realizam o mesmo papel do maestro, em que os músicos seriam os contêineres.

Atualmente, a ferramenta de orquestração mais popular e, portanto, mais solicitada no mercado de trabalho é o Kubernetes, da Google, que serve para orquestrar contêineres criados com o Docker. Importante notar que o próprio _framework_ do Docker possui uma ferramenta de orquestração nativa, instalada automaticamente com o Docker. Essa ferramenta é chamada de _**Swarm**_. Em alguns aspectos, inclusive pelo fato de ser uma ferramenta totalmente integrada com o Docker, o _Swarm_ é a mais indicada para um primeiro contato com o conceito de orquestração de contêineres.

O _Swarm_ foi integrado ao Docker a partir da versão 1.12.0, com o chamado swarm mode, em junho de 2016, conforme noticiado no blog oficial do Docker (DOCKER, [s.d.]) A figura abaixo ajudará a entender os componentes do _Swarm_ e como eles estão relacionados aos contêineres.

[![](https://ampli-images.s3.amazonaws.com/production/89c32eb2-8154-425c-a7be-310ab1862b8c/original)](https://ampli-images.s3.amazonaws.com/production/89c32eb2-8154-425c-a7be-310ab1862b8c/original)

Arquitetura do Swarm do Docker. Fonte: elaborada pelo autor.

Na figura acima, o retângulo destacado em lilás representa o que o Docker chama de Swarm, que nada mais é que um cluster (conjunto de computadores interligados que funcionam como um grande sistema), formado por vários nós, que podem rodar uma aplicação – no exemplo, o servidor web _**Nginx**_ – de maneira integrada e distribuída. Para que os nós possam estar integrados, de maneira que, caso uma instância do _Nginx_ falhe por conta de um dos nós escravos estar indisponível, esta ser automaticamente instanciada em outro nó, é necessário que exista um nó mestre que faça essa gestão.

Podem existir vários nós com a função de mestre do cluster (que o Docker chama de manager), para que, caso o nó mestre falhe, outro nó mestre assuma seu lugar. Os nós escravos (que o Docker chama de _worker_) rodam a quantidade de instâncias (frequentemente chamadas de réplicas) solicitadas pelo nó mestre e, para tal, é preciso que exista um contêiner “dentro” de cada nó escravo, o que está representado pelo retângulo laranja.