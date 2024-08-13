[![](https://ampli-images.s3.amazonaws.com/production/814cd7aa-7583-4b90-88bb-d3831f1e26c9/original)](https://ampli-images.s3.amazonaws.com/production/814cd7aa-7583-4b90-88bb-d3831f1e26c9/original)

O termo **heterogeneidade** vem de heterogêneo, ou seja, algo desigual, que apresenta estrutura, função ou distribuição diferente. Portanto, aplicando isso ao conceito de computação, quando temos heterogeneidade, estamos falando de um sistema que contenha em sua composição máquinas (nós) de sistemas operacionais, recursos (hardware) e até mesmo fabricantes diferentes. Esse é um dos aspectos mais frequentes de um sistema que utiliza arquitetura distribuída. Geralmente, o sistema é composto por máquinas de diversas características diferentes que se comunicam para manter o funcionamento.

Dessa forma, o sistema distribuído é capaz de funcionar em uma arquitetura heterogênea, tanto em termos de hardware quanto de software. Em termos de hardware, significa que o sistema distribuído consegue operar em nós com características de hardware diferentes, por exemplo, entre máquinas com diferentes valores de memória principal (RAM), memória de armazenamento (HD, SSD, etc.) e capacidade de processamento (_clock_ dos processadores).

Em termos de software, significa que o sistema distribuído suporta, por exemplo, diferentes sistemas operacionais, com alguns nós utilizando MS-Windows, enquanto outros utilizam alguma distribuição GNU/Linux. Isso pode parecer difícil de ser alcançado, mas existe um elemento que facilita nosso trabalho, o _middleware_, o qual, como o nome sugere, é uma camada de software que fica situada entre a sua aplicação e o sistema operacional.

Não se preocupe se esse termo e seu papel não estiverem claros ainda, pois detalharemos esse assunto em uma aula posterior. Por exemplo, quando um website roda em máquinas com diferentes sistemas operacionais ou características de hardware (por exemplo, uma máquina do tipo servidor que possui mais memória RAM que outra máquina dentro do mesmo sistema distribuído), dizemos que se trata de um sistema distribuído heterogêneo.

Os protocolos de redes são fundamentais para que essa comunicação entre máquinas diferentes ocorra, porém, na maioria das aplicações distribuídas, precisamos também de um _middleware_.

O _middleware_ pode ser considerado um conjunto de padrões e funcionalidades que atua como uma camada central entre a nossa plataforma, o sistema operacional e as nossas aplicações. Essa camada central permite que em um sistema distribuído rodem diferentes aplicações em diferentes plataformas e que todas elas consigam se comunicar adequadamente

Existem vários _frameworks_ utilizados para implementação de plataformas de _middleware_, e os mais conhecidos são:

- **CORBA**: _framework_ de implementação de _middleware_ baseado na linguagem de programação C++.
- **.NET Remoting**: _framework_ de implementação de _middleware_, baseado no ambiente de programação .NET, que pode utilizar várias linguagens diferentes, por exemplo, Visual Basic, C#, entre outras.
- **Akka.NET**: _framework_ de implementação de _middleware_, baseado no ambiente de programação .NET, que pode utilizar várias linguagens diferentes, como Visual Basic, C#, entre outras.
- **Java RMI**: _framework_ de implementação de _middleware_, baseado na linguagem de programação JAVA.
- **JAX-WS**: _framework_ de implementação de _middleware_, baseado na linguagem de programação JAVA.

**Segurança**

Sem dúvida, um dos aspectos mais importantes no projeto de sistemas distribuídos é a segurança. Tipicamente, seja qual for a aplicação desenvolvida, sendo um sistema distribuído, funcionará em uma plataforma com várias máquinas, chamadas de nós, que replicam tal aplicação e, conforme já sabemos, a comunicação entre essas máquinas sempre ocorre por meio de redes de comunicação, tipicamente cabeadas.

É muito importante sempre considerar aspectos de segurança no projeto de sistemas distribuídos. Segundo Coulouris _et al._ (2013), em termos de sistemas distribuídos, podemos pensar em dois níveis: o da confidencialidade e o da integridade dos dados. A confidencialidade dos dados refere-se ao acesso ao dado por indivíduos ou sistemas não autorizados, e a integridade dos dados refere-se, além do acesso, à modificação do dado.

Conforme os autores, os pontos de atenção em relação à segurança no projeto de sistemas distribuídos são:

- **Portas são expostas**: sistemas distribuídos são construídos com base em um conjunto de processos que oferecem serviços e compartilham informação. As portas de comunicação pelas quais esses serviços se comunicam são, intrinsicamente, abertas (para que clientes possam acessar tais serviços) e, dessa forma, um hacker pode enviar mensagem a qualquer uma delas.
- **Redes de computadores não são seguras**: remetentes de mensagens podem ser falsificados e endereços IP podem estar duplicados, de forma que alguém malicioso possa receber as mesmas mensagens de um destinatário válido.
- **A validade das chaves criptográficas deve ser limitada**: quanto mais tempo uma mesma chave estiver válida e ativa, maiores são as chances de estar comprometida, por ter maiores chances de ser conhecida (e explorada) por uma quantidade maior de pessoas e sistemas.
- **Algoritmos de criptografia podem ter falhas**: na atualidade, a melhor prática é divulgar publicamente os algoritmos de criptografia para que a comunidade e as entidades especialistas possam validá-lo e sugerir melhorias, de forma que a privacidade esteja garantida pela chave criptográfica, e não pela inacessibilidade ao algoritmo utilizado.
- **Hackers podem ter acesso a recursos poderosos**: o custo dos recursos computacionais tem diminuído cada vez mais, de forma que máquinas poderosas estão acessíveis para a maioria da população. Assim, sempre considere que ataques podem ocorrer de inúmeras fontes e podem explorar vulnerabilidades, utilizando, inclusive, ataques do tipo força-bruta (que tentam descobrir senhas por tentativa e erro, com simples “chutes”).