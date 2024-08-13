Uma classe importante de Sistemas Distribuídos é encontrada em organizações que se defrontam com uma grande quantidade de aplicações em rede para as quais a interoperabilidade se mostrou uma experiência dolorosa.

Muitas das soluções de middleware existente são resultados do trabalho com uma infraestrutura na qual era mais fácil integrar informações em um sistema de informações de âmbito empresarial.

À medida que as aplicações se tornavam mais sofisticadas e eram separadas em componentes independentes, separando componentes de banco de dados, de componentes de processamento, fica claro que a integração também deveria ocorrer de modo que permitisse às aplicações se comunicar diretamente umas com as outras.

Em muitos casos, uma aplicação em rede consistia em um servidor que executava uma aplicação, frequentemente incluindo um banco de dados, e a disponibilizava para programas remotos, chamados de clientes, que enviavam uma requisição ao servidor para executar uma operação específica e depois recebia uma resposta que era devolvida.

Integração em um nível mais baixo permitiria que clientes empacotassem várias requisições, que seriam enviadas para diversos servidores, em uma única requisição maior, e as enviassem para execução como uma **transação distribuída**.

Transações distribuídas abrangem dois ou mais servidores conhecidos como gerenciadores de recursos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/8/5/308509/20913.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/8/5/308509/20913.jpg)

Transação Distribuída.

Operações em um Banco de Dados costumam ser realizadas sob a forma de transações. Programar a utilização de transações requer primitivas especiais que devem ser fornecidas pelo sistema distribuído subjacente, ou pelo sistema de linguagem em tempo de execução.

O gerenciamento da transação deve ser coordenado entre os gerenciadores de recursos por um componente de servidor chamado de gerenciador de transações.

Uma transação em uma instância única de um Banco de Dados que abrange dois ou mais bancos de dados é, de fato, uma transação distribuída. A instância gerencia a transação distribuída internamente. Para o usuário, ela opera como uma transação local.

Uma transação distribuída é gerenciada da mesma forma como uma transação local. No final da transação, o aplicativo solicita que a transação seja confirmada ou revertida.

Uma confirmação distribuída deve ser gerenciada de forma diferenciada pelo gerenciador de transações para minimizar o risco de que uma falha de rede possa resultar em alguns gerenciadores de recurso que confirmam com êxito enquanto outros revertem a transação.

Isso é obtido pelo Gerenciamento do Processo de Confirmação em duas fases (**a fase de preparação** e a **fase de confirmação**), o que é conhecido como um Protocolo 2PC.

Na **Fase de Preparo**, quando o gerenciador de transações recebe uma solicitação de confirmação, ele envia um comando de preparação a todos os gerenciadores de recursos envolvidos na transação. Cada gerenciador executa todas as ações necessárias para tornar a transação durável, e todos os buffers que mantêm imagens de log da transação são liberados no disco. À medida que cada gerenciador de recursos conclui a fase de preparação, ele retorna informações de êxito ou de falha ao gerenciador de transações.

Na **Fase de Confirmação**, se o gerenciador de transações recebe preparos bem-sucedidos de todos os gerenciadores de recursos, ele enviará comandos de confirmação a cada gerenciador de recursos. Em seguida, os gerenciadores de recursos podem concluir a confirmação. Se todos os gerenciadores de recursos relatarem uma confirmação bem-sucedida, o gerenciador de transações enviará uma notificação de êxito ao aplicativo. Se um gerenciador de recursos informar uma falha na preparação, o gerenciador de transações enviará um comando de reversão a cada gerenciador de recursos e indicará a falha da confirmação ao aplicativo.

O aspecto característico de uma transação é que todas essas operações são executadas, ou nenhuma transação é executada. Elas podem ser procedimentos de biblioteca, Chamadas de Sistemas ou declarações em uma linguagem, dependendo da implementação.

Essa propriedade "tudo-ou-nada" das transações é uma das quatro propriedades características da transação, citadas como **ACID**, que são: Atômicas, Consistentes, Isoladas e Duráveis.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/9/5/309521/20914.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/9/5/309521/20914.jpg)

Propriedades ACID.

- **Atômicas**

A primeira propriedade fundamental exibida por todas as transações é que elas são atômicas (para o mundo exterior, a transação acontece como se fosse invisível).

Essa propriedade garante que cada transação aconteça completamente, ou não aconteça. Se acontecer, será como uma única ação indivisível e instantânea, ou seja, enquanto uma transação está em progresso, outros processos, estejam ou não envolvidos em transações, não podem ver nenhum dos estados intermediários.

- **Consistentes**

A segunda propriedade afirma que as transações são consistentes (a transação não viola invariantes de sistema), o que quer dizer que, se o sistema tiver certos invariantes que devem valer sempre, se eles forem válidos antes da transação, também o serão após a transação.

- **Isoladas**

A terceira propriedade diz que as transações são isoladas (transações concorrentes não interferem umas com as outras), o que significa que, se duas ou mais transações são executas ao mesmo tempo, o resultado final para cada uma delas e para outros processos se apresentará como se todas as transações fossem executadas em sequência em certa ordem, dependente do sistema.

- **Duráveis**

A quarta propriedade diz que as transações são duráveis (uma vez comprometida uma transação, as alterações são permanentes), isso quer dizer que, não importa o que aconteça, uma vez comprometida uma transação, ela continua, e os resultados tornam-se permanentes. Nenhuma falha após o comprometimento pode desfazer os resultados ou provocar sua perda.

Até aqui, as transações foram definidas em um único banco de dados. Uma transação **aninhada** é construída com base em uma quantidade de subtransações, onde a transação de nível mais alto pode se ramificar e gerar “filhos” que executam em paralelo uns aos outros, em máquinas diferentes, para obter ganho de desempenho ou simplificar a programação. Cada um desses filhos pode executar uma ou mais subtransações ou se ramificar e gerar seus próprios filhos.

Veja como funciona na figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/9/6/309631/20915.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/9/6/309631/20915.png)

Transação Aninhada.

Transações aninhadas são importantes em Sistemas Distribuídos porque proporcionam um modo natural de distribuir uma transação por várias máquinas, e seguem uma distribuição lógica do trabalho da transação original.

Vejamos um exemplo onde se quer planejar uma determinada viagem onde haverá uma reserva de três voos. Nesse planejamento uma transação pode ser dividida em até três subtransações, onde cada uma pode seer gerenciada em separado e independentemente das noutras duas.

Quando os sistemas de middleware empresarial começaram, o componente que manipulava as transações aninhadas formava o núcleo para a integração de aplicações no nível do servidor ou do banco de dados.

Esse componente era conhecido como **Monitor de Processamento de Transação**, ou simplesmente, **Monitor TP**, cuja principal tarefa era permitir que uma aplicação acessasse vários servidores de bancos de dados, oferecendo a ela um modelo de programação transacional.

A figura abaixo ilustra o funcionamento dessa integração usando um monitor TP:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/9/7/309759/20917.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/9/7/309759/20917.png)

Monitor TP em Sistemas Distribuídos.

Fonte: Figura 1.7 - pag. 14 do Livro Sistemas Distribuídos - Princípios e Paradigmas

Quanto mais as aplicações se desvinculavam dos bancos de dados sobre os quais eram construídas, mais evidente ficava que eram necessárias facilidades para integrar aplicações independentemente de seus bancos de dados.

Essa necessidade de comunicação entre aplicações resultou em muitos modelos diferentes de comunicação, tais como: **RPC** (Chamada de Procedimento Remoto); **RMI** (Invocações de Método Remoto); **MON** (Middleware Orientado a Mensagem).

Na figura abaixo, apresentamos um esquema de middleware como um facilitador de comunicação integrando aplicações empresariais:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/9/7/309761/20920.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/9/7/309761/20920.png)

Middleware de Comunicação.

Fonte: Figura 1.8 pag. 14 do Livro Sistemas Distribuídos Princípios e Paradigmas

**CONTROLE DE CONCORRÊNCIA**

Controle de concorrência é um método usado para garantir que as transações sejam executadas em paralelo, de uma forma segura e sigam as regras ditadas por ACID.

Os SGBD (Sistema Gerenciador de Banco de Dados) devem ser capazes de assegurar que nenhuma ação de transações completadas com sucesso seja perdida ao desfazer transações abortadas.

Uma transação é uma unidade que deve preservar a consistência, portanto, qualquer escalonamento produzido ao processar um conjunto de transações concorrentemente, deve ser computacionalmente equivalente a um escalonamento que execute essas transações serialmente em alguma ordem.

Diz-se que um sistema que garanta essa propriedade assegura a seriabilidade.

Dessa forma, qualquer transação que pretenda atualizar um registro, primeiro terá que acessar aquele registro e bloqueá-lo exclusivamente. Se o bloqueio não puder ser feito, a transação entra em um estado de espera e apenas continuará o processamento quando o registro estiver disponível e o bloqueio puder ser concedido.

O sistema terá que garantir que uma transação forçada a esperar por causa desse protocolo, eventualmente sairá do estado de espera. Para evitar a possibilidade de perda de atualizações, nenhuma transação poderá ter acesso aos dados de uma atualização não efetuada.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/7/5/307548/20924.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/7/5/307548/20924.png)

Controle de Concorrência.

Como sistemas computacionais podem executar vários processos de forma concorrente, existe a possibilidade de concorrência entre transações e, ainda, a concorrência no acesso à base de dados por estas transações.

Para evitar problemas como conflitos, é necessário um controle seguro de acesso a objetos por parte das transações para permitir a perfeita concorrência de processamento entre estas transações ou, no caso da ocorrência de deadlocks, onde duas ou mais transações esperam em estado simultâneo, deve possibilitar a detecção destes casos e a devida solução.

Para solucionar estes casos, existem várias técnicas que permitem evitar ou contornar casos de conflitos, são elas: **two-phase locking** e **optimistic locking**.

Em **two-phase locking**, cada transação possui duas fases no que tange o acesso a objetos. A primeira fase é aquela na qual a transação obtém o bloqueio de todos os objetos que serão utilizados no seu processamento. Na segunda fase, existe o processamento e a efetivação dos resultados com o consequente desbloqueio dos objetos usados.

Esta técnica garante que não irão ocorrer conflitos durante o processamento, já que a transação só irá prosseguir caso obtenha o controle dos objetos necessários. Com isto evita-se o problema de solucionar deadIocks, com a execução já parcialmente realizada por parte das transações.

No caso do **optimistic locking**, assume-se que a ocorrência de conflitos será mínima, sendo, portanto desprezado o controle de concorrência.  Neste caso, todas as alterações realizadas pela transação são armazenadas até o seu final, quando irão ser ou não processadas.

Se forem permitidas as alterações, e se outra transação não modificou o estado inicial dos objetos a serem alterados, a transação encerra normalmente. Caso contrário, a transação será abortada e seus resultados abandonados.

O controle de concorrência é muito utilizado em transações de banco de dados, sistema como ORACLE, Mysql, MS SQL SERVER utilizam estes métodos.