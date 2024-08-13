Em Sistemas Distribuídos baseados em objetos, a noção de um objeto desempenha papel fundamental no estabelecimento da transparência da distribuição, uma vez que tudo é tratado como objeto, e os serviços e recursos são oferecidos a clientes na forma de objetos os quais eles podem invocar.

A orientação para objetos é um padrão importante em desenvolvimento de software, e desde seu surgimento (década  de 1980) teve grande popularidade, pois se origina da capacidade de embutir software em componentes bem definidos e mais ou menos independentes.

A característica fundamental de um objeto é que ele encapsula dados, e são denominados de **estado**, e as operações executadas por esses dados são chamadas de **métodos**, que são disponibilizados por meio de uma interface.

Não há nenhuma outra forma de um processo acessar ou manipular o estado de um objeto, que não seja por meio de uma interface de objeto, sendo que este pode implementar várias interfaces.

A separação que existe entre a interface e um objeto é muito importante para Sistemas Distribuídos, pois essa separação permite colocar uma interface em uma máquina, enquanto o objeto reside em outra máquina.

Essa organização existente entre a interface e um objeto, é chamada de **objeto distribuído**, e é demonstrada na figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/7/301784/19602.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/7/301784/19602.png)

Organização de um Objeto remoto

Fonte: Figura 10.1 - Pág. 269 do Livro Sistemas Distribuídos - Princípios e Métodos

Assim, quando um cliente se vincula a um objeto distribuído, uma implementação da interface do objeto (proxy) é carregada no espaço de endereços do cliente. Seu objetivo é montar invocações a métodos de passagens e desmontar mensagens de resposta para retornar o resultado da invocação do método ao cliente.

O objeto propriamente dito reside em uma máquina do servidor, onde oferece a mesma interface que existe na máquina do cliente e o apêndice servidor, chamado de esqueleto, também é responsável por montar respostas e expedir mensagens de resposta para o proxy do cliente.

Objetos em Sistemas Distribuídos aparecem de várias formas, sendo uma delas relacionada diretamente com os objetos de nível de linguagem, como os suportados por JAVA, C++, entre outras linguagens orientadas a objetos, que são chamadas de objetos de tempo de compilação.

Nesse caso, os objetos são tratados como a instância de uma **classe**. Meyer (1997) define a classe como uma descrição de um tipo de abstrato em termos de um módulo com elementos de dados e operações sobre esses dados.

Um modo alternativo de construir objetos distribuídos é fazê-lo durante o tempo de execução, o que é adotado por muitos sistemas distribuídos baseados em objetos, uma vez que eles são independentes da linguagem de programação na qual as aplicações são desenvolvidas.

**OBJETOS PERSISTENTES E TRANSIENTES**

Um **objeto persistente** é aquele que continua a existir mesmo que não esteja contido no espaço de endereços de qualquer processo servidor, pois ele não depende de seu servidor corrente. Isso significa que o servidor que está gerenciando o objeto persistente pode armazenar o estado do objeto em um armazenamento secundário e em seguida sair, o que permite que outro servidor leia o estado do objeto levando-o para seu próprio espaço de endereços, manipulando as requisições de invocação.

Por outro lado, um **objeto transiente** é um objeto que existe somente enquanto existir o servidor que o está hospedando, e tão logo esse servidor saia, o objeto deixa de existir.

A maioria dos Sistemas Distribuídos baseados em objetos suportam ambos os tipos.

**ENTERPRISE JAVA BEANS**

Desde sua implantação, a linguagem de programação Enterprise Java Beans (EJB) teve como objetivo prover recursos que facilitassem o desenvolvimento de aplicações distribuídas, exigindo um ambiente de tempo de execução que suporte arquiteturas cliente-servidor multi camadas tradicionais.

A linguagem de programação em Java forma a base para numerosos sistemas e aplicações distribuídos. Sua popularidade deve-se ao suporte direto à orientação a objetos, combinado com o suporte inerente para invocação de método remoto.

Um EJB é um objeto em Java hospedado por um servidor especial que oferece aos clientes remotos modos diferentes para invocar um objeto. É importante que esse servidor forneça suporte para separar funcionalidade de aplicação, de funcionalidade orientada a sistemas, uma vez que estas incluem funções para consultar objetos, armazenar objetos e permitir que objetos façam parte de uma transação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/3/299316/19603.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/3/299316/19603.png)

Arquitetura geral de um servidor EJB

Fonte: Figura 10.2 - Pág. 270 do Livro Sistemas Distribuídos - Princípios e Métodos

O que se observa na figura é que um EJB é embutido em um contêiner que efetivamente provê interfaces para serviços subjacentes que são implementados pelo servidor de aplicação.

O contêiner pode vincular o EJB com seus serviços o que significa que referências corretas estarão disponíveis para os programadores. Serviços oferecidos pelo EJB: Invocação de Método Remoto (RMI); Acesso a Banco de Dados (JDBC); Nomeação (JNDI) e Troca de Mensagens (JMS).

A utilização desses serviços é automática, mas o programador deve escolher entre quatro espécies de EJB's: Bean de sessão sem estado; Bean de sessão com estado; Beans de entidade e Beans acionados por mensagem.

**Bean de sessão sem estado**

É um objeto transiente que é invocado uma vez, executa seu trabalho e depois descarta qualquer informação que precisou para executar o serviço oferecido ao cliente.

Esse tipo de Bean pode ser usado para implementar um serviço que apresente uma lista dos vinte carros mais vendidos no Brasil. Isso aconteceria realizando uma consulta SQL apresentada a um banco de dados. Após a apresentação do resultado ao cliente seu trabalho estaria concluído e a lista seria descartada.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296806/19604.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296806/19604.jpg)

Exemplo de lista montada por Bean de Sessão sem Estado.

**Bean de sessão com estado**

O Bean de sessão com estado mantém o estado relacionado ao cliente, por exemplo, imagine um carrinho de compra eletrônico igual aos utilizados em comércio eletrônico, onde um cliente coloca suas mercadorias no carrinho, pode remover ou incluir novos itens e efetuar o pagamento quando necessário. Esse tipo de Bean acessa bancos de dados para obter preços correntes e outras informações referente aos itens existentes em estoque.

Mesmo assim, ele tem sua vida útil limitada, uma vez que no momento em que o cliente termina sua operação, o Bean é automaticamente removido.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296807/19605.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296807/19605.jpg)

Compra eletrônica - adicionando produtos no carrinho.

**Beans de entidade**

Pode ser considerado um objeto persistente de longa vida, que será armazenado em um banco de dados, cujas informações poderão ser utilizadas da próxima vez que um determinado cliente participar de transações distribuídas futuras.

Esse tipo de Beans armazena dados do tipo: endereço de entrega, endereço de cobrança, número do cartão de crédito, nome, data de nascimento, entre outras informações.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296808/19606.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296808/19606.jpg)

Exemplo de guarda de mensagens.

**Beans acionados por mensagem**

São usados para programar objetos que vão reagir às mensagens que chegam e as mensagens enviadas.      Eles não podem ser invocados diretamente por um cliente, mas devem se ajustar a um modo de comunicação.

Um Bean acionado por mensagem é chamado automaticamente pelo servidor quando uma mensagem é recebida. Permite através de alguns códigos de comunicação que a mensagem seja manipulada e depois o servidor a descarta.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296809/19607.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296809/19607.jpg)

Exemplo de envio e recebimento de mensagem.