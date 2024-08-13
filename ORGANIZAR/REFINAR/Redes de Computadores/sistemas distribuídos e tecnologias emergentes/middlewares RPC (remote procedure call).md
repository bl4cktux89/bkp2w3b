Um middleware pode ser visto como uma camada de software intermediária localizada entre o sistema operacional e as aplicações distribuídas, tendo como objetivo abstrair a heterogeneidade existente da comunicação distribuída.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/0/297066/19736.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/0/297066/19736.png)

Sistema distribuído organizado como middleware. A camada de middleware se estende por várias máquinas e oferece a mesma interface a cada aplicação.

Fonte: Figura 1.1 - Pag. 2 do Livro Sistemas Distribuídos - Princípios e Paradigmas.

Inicialmente, um Middleware tinha a função básica de unir os componentes de um programa distribuído, ditando a maneira pela qual estes componentes interoperavam. Atualmente, sua função é integrar aplicações completas entre e dentro das organizações.

A camada de Middleware concentra serviços como identificação, autenticação, autorização, diretórios, certificados digitais e outras ferramentas para segurança.

Aplicações tradicionais implementam vários desses serviços, tratados de forma independente por cada uma delas. As aplicações modernas, no entanto, delegam e centralizam estes serviços na camada de Middleware.

Um ponto importante na utilização e funcionalidade dos Middlewares é a sua padronização, o que causa problemas relacionados à integração, facilidade de uso e gerenciamento. Entretanto, a padronização é importante para auxiliar os clientes a selecionarem Middlewares baseados em qualidade.

Duas características importantes na construção de um Middleware são sua flexibilidade e performance, já que o alto nível de flexibilidade acaba impedindo um alto nível de performance, sendo o ideal um balanceamento entre os dois.

Referente à integração entre aplicações escritas em diferentes linguagens de programação, poucos Middlewares suportam esta característica. Um exemplo de integração entre diferentes linguagens é o CORBA (Commom Object Request Broker Architecture), que permite fazer o mapeamento de uma IDL (Interface Definition Language) em muitas linguagens de programação. E também, seu concorrente o DCOM (Distributed Component Object Model) que é uma solução distribuída do COM (Component Object Model) da Microsoft.

Vejamos a seguir essas duas soluções de Middleware:

**CORBA**

O **CORBA** (Common Object Request Broker Architecture) é uma solução de desenvolvimento de software baseado em duas características importantes: a orientação a objetos e o modelo Cliente/Servidor.

A solução foi criada em 1989 pela OMG (Object Management Group) para o desenvolvimento de soluções heterogêneas e orientadas a objetos CORBA.

As solicitações que são enviadas pelos clientes e as respostas do servidor ocorrem através de **ORB** (Object Request Broker - Agente de Requisição de Objetos).

Cada ORB possui uma especificação de serviços e regras de negócios diferentes. Assim, cada cliente poderá fazer a sua requisição ao objeto ORB que atenderá dentro do que foi especificado. É a IDL (Interface Definition Language) que trata dessas especificações.

Como a solução poderá ter diversos objetos ORB, cada um deles recebe um identificador único para que seja possível diferenciá-los tanto do lado do cliente, quanto do servidor.

Cada objeto na arquitetura CORBA pode ser desenvolvido em uma linguagem de programação diferente e estar em localizações geográficas diferentes, e este cenário é totalmente favorável, principalmente nos temas de heterogeneidade, interoperabilidade e portabilidade da solução.

O cliente possui contato diretamente com a interface do software, que por sua vez, deve ter contato direto com os objetos que devem receber as suas requisições. Assim, o cliente se comunica com o objeto através dos **stubs** e dos **skeletons**, que são dois componentes que fazem parte da arquitetura CORBA.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/3/297316/19737.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/3/297316/19737.png)

Estrutura da arquitetura cliente/servidor do CORBA

Fonte: Retirada de uma aula AVA anteriormente desenvolvida.

Os Stubs ficam na extremidade do cliente e os Skeletons nos objetos servidor. Assim, o cliente apenas informa qual o objeto que precisa e o stub se encarrega de empacotar a mensagem para o objeto. Desta forma, o cliente não precisa se preocupar em saber onde o objeto está localizado geograficamente, ou seja, se está local ou distante.

O ORB encaminhará a mensagem ao Skeleton que entregará ao objeto que processará a requisição. A comunicação da resposta (a volta) ao cliente funciona exatamente como na ida.

Em suma, o CORBA é um RPC que permite realizar invocação remota de objetos pela rede local, de média ou longa distância.

**DCOM**

O DCOM (Distributed Component Object Model) é uma solução distribuída do COM (Component Object Model) da Microsoft e possui dependência apenas do Sistema Operacional que deve ser o MS Windows.

O início do COM se deu a partir do OLE (Object Linking and Embedding) criado em 1990 com objetivo de permitir que documentos em diversas aplicações pudessem manipular tipos de dados multimídia.

Além disso, as soluções com o OLE Automation (sucessor do OLE), ActiveX, COM e COM+ (COM Plus) antecederam o DCOM. O COM, por sua vez, foi projetado para ser uma solução orientada a objeto e interoperável.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/2/297261/19738.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/2/297261/19738.png)

Estrutura de Comunicação COM

Fonte: Comunicação entre o Cliente, o Componente COM e o Servidor

É importante destacar que o DCOM é uma solução de RPC que oferece serviços de orientação a objetos aos clientes e componentes, além de oferecer os serviços de provedor de segurança para que os pacotes gerados estejam alinhados ao padrão DCOM.

Os objetos devem ser solicitados através do  SCM (Service Control Manager) e são identificados na classe chamada Class Identifier (CLSID).

O DCOM faz o uso do DCE (Distributed Computing Environment ou Ambiente de Computação Distribuída) para implementar os conceitos de RPC.

A arquitetura DCOM pode ser desenvolvida nas linguagens de programação C# (C Sharp), VB.Net (Visual Basic .Net) e ASP.Net (Active Server Pages .Net) que são linguagens proprietárias da Microsoft.

Neste sentido, o DCOM pode ser criado para consumir recursos de um Web Service (WS) e, neste caso, o Web Service pode ser criado em outra linguagem de programação, como por exemplo o JAVA e o PHP (Hypertext Preprocessor).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297448/19741.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297448/19741.png)

Comunicação entre o cliente, o componente DCOM e o servidor.

**RPC** (Remote Procedure Call - Chamada de Procedimento Remota)

RPC é uma tecnologia de [**comunicação entre processos**](http://pt.wikipedia.org/wiki/Comunica%C3%A7%C3%A3o_entre_processos) que permite a um programa de computador chamar um procedimento em outro espaço de endereçamento (geralmente em outro computador, conectado por uma [**rede**](http://pt.wikipedia.org/wiki/Rede_de_computadores)).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297449/19744.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297449/19744.png)

Princípio da comunicação RPC entre Cliente e Servidor.

Fonte: Figura 4.6 - Pag. 77 do Livro Sistemas Distribuídos - Princípios e Paradigmas.

A RPC consegue sua transparência de modo análogo, ou seja, através de um procedimento remoto, que executará na máquina do servidor de arquivo. Ela faz uma chamada ao Sistema Operacional local, mas não pede que lhe dê dados, em vez disso, empacota os parâmetros em uma mensagem e requisita que essa mensagem seja enviada ao servidor, conforme demonstrado na figura acima.

Quando essa mensagem chega ao servidor o Sistema Operacional a passa para o apêndice de servidor, que é um equivalente ao apêndice de cliente, que transforma requisições  que vem pela rede em chamadas de procedimento locais.

Assim, o apêndice do servidor desempacota os parâmetros da mensagem e chama o procedimento do servidor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297450/19746.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297450/19746.png)

Passagem de parâmetros em uma chamada de procedimento local.

Fonte: Figura 4.5 - Pag. 76 do Livro Sistemas Distribuídos - Princípios e Paradigmas.

O programador não se preocupa com detalhes de implementação dessa interação remota: do ponto de vista do código, a chamada se assemelha a chamadas de procedimentos locais. E do ponto de vista do servidor, é como se ele fosse chamado diretamente pelo cliente, uma vez que os parâmetros e endereço de retorno estão todos na pilha à qual pertencem e nada parece estar fora do normal.

Assim, o servidor executa o seu trabalho e retorna o resultado ao chamador do modo usual.

O RPC permite também, que um programa procedural, que apresente os procedimentos (passo-a-passo), chame uma função que reside em outro computador tão convenientemente como se essa função fosse parte do mesmo programa que executa no mesmo computador.

O objetivo do RPC foi permitir aos programadores se concentrar nas tarefas exigidas de um aplicativo, e ao mesmo tempo, tornando transparente para o programador o mecanismo que permite que as partes do aplicativo se comuniquem através de uma rede.

A maior vantagem do RPC é a chamada de métodos em outras linguagens, pois ele não é focado em uma linguagem específica, o que resulta em uma maior flexibilidade.