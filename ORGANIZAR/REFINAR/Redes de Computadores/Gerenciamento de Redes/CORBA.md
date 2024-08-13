**Introdução**

Olá, bem-vindos;

Nesta aula falaremos sobre o CORBA, uma arquitetura criada para troca de dados entre sistemas de diferentes padrões.

CORBA (_**Common Object Request Broker Architecture**_) é uma arquitetura criada pelo _**Object Management Group**_ para estabelecer e simplificar a troca de dados entre sistemas distribuídos heterogêneos.

Atualmente, há softwares e hardwares dos mais variados fabricantes, que, em muitos casos, são incompatíveis. Nesse ambiente atua o CORBA, de forma que os objetos (componentes dos softwares ou hardwares) possam se comunicar transparentemente, em especial com o usuário, mesmo que um software intermediário seja necessário. CORBA é um dos modelos mais populares de objetos distribuídos, juntamente ao DCOM da Microsoft.

**ORB**

A estrutura do CROBA trabalha com um módulo intermediário chamado ORB (_**Object Request Broker**_), que atua para aceitar requisições de um cliente e encaminhá-las a um objeto, e também no sentido inverso.

**IDL**

A linguagem utilizada pelo CORBA é a IDL (_**Interface Definition Language**_), uma linguagem derivada da linguagem C++, que não possui algoritmos nem variáveis, ela é puramente declarativa. Assim, independe de qualquer linguagem para acessá-la. Logo, existem IDL, definidos pelo OMG para C, C++, JAVA, COBOL e outras linguagens.

**Persistência**

A arquitetura do CORBA define o POS (_**Persistent Object Service**_) para garantir persistência entre objetos, ao contrário dos objetos tradicionais, que possuem dualidade como característica: um estado dinâmico e um estado persistente. O estado dinâmico reside em memória volátil. Dessa maneira, o estado é perdido quando não há mais execução; já no estado persistente, o objeto é armazenado em uma memória não volátil. Portanto, o programa que os criou pode ser usado para reconstruir o estado dinâmico – similar aos recursos de memória virtual dos sistemas operacionais.

O POS utiliza quatro elementos para armazenar o estado persistente dos objetos, são eles:

- Objetos Persistentes (_Persistent Object – POs_)
- Gerenciador de Objetos Persistentes (_Persistent Objects Manager – POM_)
- Serviços de Persistência de Dados (Persistent Data Services – PDSs)
- Base de Dados (Datastores)