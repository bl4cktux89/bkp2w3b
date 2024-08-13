### Processos

Os sistemas operacionais modernos, segundo Sobell ([1]), são geralmente multitarefa, o que significa que eles criam a ilusão de fazer mais do que uma coisa ao mesmo tempo, passando rapidamente de um programa de execução para outro. O kernel do Linux gerencia isso através do uso de processos. Processos são como o Linux organiza os diferentes programas esperando por sua vez na CPU. Às vezes, um computador fica lento ou um aplicativo pára de responder. Neste tópico, veremos algumas das ferramentas disponíveis de linha de comando que nos permitem examinar o que programas estão fazendo e como encerrar processos que estão se comportando mal.

Este tópico apresentará os seguintes comandos:

ps – Mostra um instantâneo dos processos em execução.

top – Mostra as tarefas.

jobs – Lista os trabalhos (jobs) em execução.

bg – Coloca um job em background (execução em segundo plano).

fg – Coloca um job em foreground (execução em primeiro plano)

kill – Mando um sinal (signal) para um processo.

killall – Mata/cancela os processos pelo nome.

shutdown – Desligar ou reiniciar o sistema.

### O Mecanismo do Processo

Quando o sistema é iniciado, o kernel inicia algumas de suas próprias atividades em formato de processo e lança um programa chamado init. O init, por sua vez, executa uma série de scripts shell (localizados no diretório /etc) chamado init scripts, que iniciam todos os serviços do sistema. Scripts shell são conjuntos de comandos de linha guardados em um arquivo para executarem determinadas tarefas. Muitos desses serviços são implementados como programas do daemon, programas rodam em background e realizam suas atividades sem qualquer interface com o usuário. Assim, mesmo que não estejamos conectados, o sistema está ocupado executando coisas de rotina. O fato de um programa poder lançar outros programas ocorre quando um processo pai produz um processo filho. Caso queira se aprofundar mais no assunto, este mecanismo está bem explicado em [2].

O kernel mantém informações sobre cada processo para ajudar a manter as coisas organizadas. Por exemplo, a cada processo é atribuído um número chamado ID de processo ou PID. Os PIDs são numerados em ordem crescente, com init sempre recebendo PID 1. O kernel também mantém trilha da memória atribuída a cada processo, bem como a prontidão dos processos para execução. Como arquivos, os processos também possuem proprietários e IDs de usuário, IDs de usuário efetivos, etc.

### Listando os Processos

O comando normalmente usado para visualizar processos é o “ps”. O programa “ps” tem muitas opções, mas em sua forma mais simples é usado como este:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823678/36769-01.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823678/36769-01.png)

Como resultado listou dois processos, processo **11975** e processo **12049**, que são: bash e ps, respectivamente. Como podemos ver, por padrão, ps não nos mostra muito, apenas os processos associados à sessão de terminal atual. Para ver mais, precisamos adicionar algumas opções, mas antes de fazer isso, vamos olhar para os outros campos produzidos pelo ps. TTY é a abreviação de "Teletype" e refere-se ao terminal de controle do processo. O campo TIME é a quantidade de tempo de CPU consumida pelo processo. CMD é o nome do processo e PID é o número do processo.

Se adicionarmos uma opção, podemos obter uma imagem melhor do que o sistema está fazendo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823682/36769-02.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823682/36769-02.png)

Adicionando a opção "x" (note que não há nenhum hífen) diz ao ps para mostrar todos os nossos processos independentemente de qual terminal (se houver) os está executando. A presença de um "?" na coluna TTY indica que o processo não é controlado por nenhum terminal. Usando esta opção, vemos a lista de processos que possuímos. Uma vez que o sistema esteja executando muitos de processos, o ps produzirá uma longa lista. Muitas vezes é útil redirecionar a saída de ps para facilitar a visualização. Algumas combinações de opções podem produzir longas listas de saída, de modo que, maximizar a janela do emulador de terminal pode ser uma boa ideia.

Uma nova coluna intitulada STAT foi adicionada à saída. STAT é abreviação de "estado" e revela o estado atual do processo. Veja os significados abaixo.

- **R** > O processo está executando ou pronto para executar.
- **S** -> O processo está dormindo. Pode estar esperando que seja pressionado uma tecla ou aguardando um evento de rede.
- **D** -> O processo está parado e não pode ser “acordado”, pois está esperando uma entrada ou saída, como lendo ou colocando dados no disco.
- **T** > O processo está parado.
- **Z** -> É um processo “zumbi”. Está dormindo, mas não pode ser encerrado porque depende de seu processo pai.
- **<** -> É um processo de alta prioridade.
- **N** -> É um processo de baixa prioridade.

O estado do processo pode ser seguido por outros caracteres. Estes indicam características do processo. Consulte a página do manual do ps para obter mais detalhes.

Outra opção popular é o  "aux" (sem hífen). Isso nos dá ainda mais em formação:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823683/36769-03.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823683/36769-03.png)

Este conjunto de opções (a+u+x) exibe os processos pertencentes a cada usuário. Usando as opções sem o hífen, invoca o comando "estilo BSD". A versão Linux do ps pode emular o comportamento do programa ps encontrado em várias implementações Unix. Com essas opções, obtemos essas colunas adicionais:

Header Meaning

USER User ID. This is the owner of the process.

%CPU CPU usage in percent.

%MEM Memory usage in percent.

VSZ Virtual memory size.

RSS Resident Set Size. The amount of physical memory (RAM) the process is using in kilobytes.

START Time when the process started. For values over 24 hours, a date is used.

- **USER** - O usuário proprietário do processo.
- **%CPU** - Porcentagem de uso da CPU pelo processo.
- **%MEM** - Porcentagem de uso da memória principal pelo processo.
- **VSZ** - Quantidade de memória virtual usada pelo processo.
- **RSS** - Quantidade real de memória principal que a parte ativa do processo está usando.

### Observando Dinamicamente os Processos

Enquanto o comando ps pode revelar muito sobre o que a máquina está fazendo, ele fornece apenas um instantâneo do estado da máquina no momento em que o comando ps é executado. Para ver uma visão mais dinâmica da atividade da máquina, usamos o comando TOP, como podemos ver abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823684/36769-04.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823684/36769-04.png)

O programa top exibe um display de atualização contínua (por padrão, a cada 3 segundos) dos processos do sistema listados por ordem de atividade do processo, ou seja, quanto mais uso de CPU, mais acima da lista o processo aparece. O nome "top" vem de o fato de que o programa top ser usado para ver os processos "top" no sistema. O cabeçalho é composto por duas partes: um resumo do sistema no primeiro, seguido de uma tabela de processos ordenados por atividade da CPU.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823685/36769-05.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823685/36769-05.png)

Vamos observar o cabeçalho:

- Top Nome do comando que está sendo executado
- 11:56:00 Horário no qual o comando foi executado
- Up 3 days, 1:47 Tempo que o sistema está no ar (rodando) desde o último restart.
- 1 user Número de usuários conectados na máquina.
- Load average 0,09 Número de processos disputando CPU nos últimos 60 segundos, nos últimos 5 minutos e nos próximos 15 minutos.
- Tarefas/Tasks Mostra o total de processos e os processos em cada tipo de estado
- %Cpu (s) Descreve os vários tipos de uso da CPU.
- 0,3 us 30% da CPU está sendo usada por processos de usuário
- 0,3 sy 30% da CPU está sendo usada por processos de kernel.
- 0,1 ni 1% da CPU está com processos “nice” (baixa prioridade)
- 99,2 id 99,2% da CPU está idle. (Ociosa)
- 0,1 wa 10% da CPU está esperando por I/O
- 0,0 hi 0% da CPU está sendo usada por interrupções de hardware
- 0,0 si 0% da CPU está sendo usada por interrupções de software
- 0,0 st 0% da CPU aguardando a cpu virtual (em caso de hypervisors)
- KiB Mem A forma com a memória principal está sendo usada
- KiB Swap A forma com a memória de swap está sendo usada

O programa top aceita vários comandos de teclado. Os dois mais interessantes são o “h”, que exibe a tela de help, e o “q”, que sai/termina comando. Os principais ambientes de desktop fornecem aplicativos gráficos que exibem informações semelhantes ao top, mas o top é melhor do que as versões gráficas porque é mais rápido e consome muito menos recursos do sistema. Mesmo porque, um programa de monitoramento de sistema não deve consumir parte do sistema que estamos tentando analisar/controlar.

### Controlando os Processos

Com os comandos acima podemos observar, analisar e monitorar os processos. Agora vamos controlá-los.

Para nossos exemplos, vamos usar um pequeno programa chamado **xlogo** como teste. O programa **xlogo** é um programa de exemplo fornecido com o X Window System (o sistema

“motor” que faz com que os gráficos sejam apresentados) que simplesmente exibe uma janela redimensionável  que contém o logotipo X. Antes, vamos conhecer nosso ambiente para teste:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823686/36769-06.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823686/36769-06.png)

Depois de inserir o comando, uma pequena janela contendo o logotipo deve aparecer em algum lugar na tela. Em alguns sistemas, o xlogo pode imprimir uma mensagem de aviso, mas pode ser ignorado com segurança.

Podemos verificar se o xlogo está sendo executado redimensionando sua janela. Se o logotipo for redesenhado para novo tamanho, o programa está em execução. Observe como o prompt do shell não retornou. Isso ocorre porque o shell está aguardando o xlog terminar, assim como todos os outros programas que usamos até agora. Se fecharmos o Xlogo, o prompt retorna. Se você quer um prompt enquanto os programas estão segurando algum shell, abra outro terminal.

Vamos observar o que acontece quando executamos xlogo novamente. Primeiro, digite o comando xlogo. Verifique se o programa está em execução. Em seguida, volte à janela do terminal e pressione Ctrl-c.

Pressionar Ctrl-c em um terminal, interrompe um programa em execução. Isso significa que pedimos educadamente para o programa para terminar. Depois de pressionar Ctrl-c, a janela do xlogo foi fechada e o prompt do shell retornado. Muitos (mas não todos) programas de linha de comando podem ser interrompidos usando esta técnica.

### Colocando um processo em segundo plano

Digamos que queríamos obter o prompt do shell sem terminar o xlogo. Podemos fazer isso colocando o programa em segundo plano. Pense no terminal como algo em primeiro plano (com coisas visíveis na superfície como o shell prompt) e um segundo plano com coisas escondidas atrás da superfície. Para iniciar um programa em segundo plano, acrescentamos ao comando com um caractere "&":

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823687/36769-07.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823687/36769-07.png)

Depois de digitar o comando, a janela **xlogo** apareceu e o prompt do shell retornou, mas alguns números foram mostrados também. Esta mensagem é parte de um recurso de shell chamado

Controle do trabalho. Com esta mensagem, o shell está nos dizendo que começamos o trabalho número **1 ("[1]")** e que tem PID **21683**. Se executarmos ps, podemos ver o nosso processo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823688/36769-08.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823688/36769-08.png)

A facilidade de controle de tarefas do shell também nos dá uma maneira de listar os trabalhos que foram lançados do nosso terminal. Usando o comando jobs, podemos ver esta lista:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823689/36769-09.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823689/36769-09.png)

Os resultados mostram que temos um trabalho, numerado **"1"**, que está sendo executado, e que o comando foi xlogo &.

### Retornando um processo para o primeiro plano

Um processo em segundo plano é imune a entrada de teclado, incluindo qualquer tentativa de interrupção

Com um Ctrl-c. Para retornar um processo para o primeiro plano, use o comando **fg**, da seguinte forma:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823690/36769-10.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/6/823690/36769-10.png)

O comando fg seguido por um sinal de porcentagem e o número do trabalho (chamado jobspec) faz a mágica. Se tivermos somente um job em segundo plano, o jobpec é opcional. Para terminar xlogo, pressione Ctrl-c.

### Parando (pausando) um processo

Às vezes, queremos parar um processo sem terminá-lo. Isso geralmente é feito para permitir que um processo de primeiro plano possa ser movido para o segundo plano. Para interromper um processo de primeiro plano, pressione Ctrl+z. Vamos tentar. No prompt de comando, digite xlogo, a tecla Enter e Ctrl+z:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830958/untitled-1-01.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830958/untitled-1-01.png)

Depois de parar xlogo, podemos verificar se o programa parou tentando redimensionar a janela xlogo. Vamos perceber que o programa parece inoperante. Podemos restaurar o programa para o primeiro plano, usando o comando fg, ou mover o programa para o segundo plano com o comando bg:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830962/untitled-1-02.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830962/untitled-1-02.png)

Como com o comando **fg**, no bg o jobpec é opcional se houver apenas um job. Mover um processo do primeiro plano para o segundo plano é útil se lançarmos um software gráfico, mas não esqueça de colocá-lo em segundo plano adicionando o “&".Existem duas razões para você executar um programa gráfico via comando de linha, no lugar de clicar no ícone correspondente no ambiente gráfico. A primeira razão é se o programa que você deseja executar não estiver listado na janela, como é o caso do **xlogo**. A segunda é: ao lançar um programa a partir do comando de linha, você pode ser capaz de ver mensagens de erro que, caso contrário, seria invisível se o programa fosse lançado graficamente. Às vezes, um programa não seria iniciado lançado a partir do menu gráfico, mas ao iniciá-lo a partir da linha de comando pode-se ver uma mensagem de erro que iria revelar o problema. Além disso, alguns programas gráficos têm muitas opções de linha de comando interessantes e úteis.

### Enviando Sinais para os Processos

O comando kill é usado para "matar" processos. Isso nos permite encerrar programas que precisam ser encerrados. Veja o exemplo abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830963/untitled-1-03.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830963/untitled-1-03.png)

Primeiro lançamos xlogo em segundo plano. O shell imprime o jobpec e o PID doProcesso em segundo plano. Em seguida, usamos o comando kill e especificamos o PID do processo que queremos terminar com o **ps**. Poderíamos também ter especificado o processo usando um jobpec (por exemplo, "% 1") em vez de um PID. O comando kill não só "mata" processos, mas, sim, envia-lhes sinais. Os sinais são uma das várias maneiras que o sistema operacional se comunica com os programas. Já vimos sinais em ação com o uso de Ctrl-c e Ctrl-z. Quando o terminal recebe estas teclas/inputs, envia um sinal para o programa em primeiro plano. No caso de Ctrl-C, é enviado um sinal chamado INT (Interrupção); Com Ctrl-z, um sinal chamado TSTP (Terminal, Pare/Stop). Por sua vez, ao "ouvir" os sinais, os programas podem agir de acordo com eles. O fato de que um programa poder ouvir e agir sobre sinais permite que um programa faça coisas como salvar trabalhos em andamento quando é enviado um sinal de encerramento.

O comando kill é usado para enviar sinais para os programas. Sua sintaxe mais comum é:

- **kill [-sinal] PID**

Se nenhum sinal for especificado na linha de comando, então o sinal TERM (Terminate/encerre) é enviado por padrão. O comando kill é mais usado para enviar os seguintes sinais:

- **1** - Hangup. Quer dizer “desconecte o terminal”. Todos os jobs do terminal serão encerrados.
- **2** - Interrupt. É o mesmo que Ctrl-C.
- **9** - Kill. Às vezes o programa não encerra. Você deve forçar com “9”. Mas cuidado: Com este sinal forçado, o programa não tem tempo de salvar os trabalhos. Somente use em casos de emergência ou quando não há risco de perder dados.
- **15** - Terminate. Encerra processos que estão ativos.
- **19** - Stop. Para os processos.
- **18** - Continue. Faz com que os processos parados (10 -stop) sejam continuados.

Vamos experimentar os sinais:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830966/untitled-1-04.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830966/untitled-1-04.png)

Neste exemplo, iniciamos o programa **xlogo** em segundo plano e, em seguida, enviamos um sinal HUP com o Kill. O programa xlogo termina e o shell indica que o background recebeu um sinal de hangup com o comando. Talvez seja necessário pressionar a tecla enter algumas vezes antes de a mensagem aparecer. Note que os sinais (1, 2, 9... etc.) podem ser especificados número ou por nome, incluindo o nome com as letras "SIG":

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830968/untitled-1-05.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830968/untitled-1-05.png)

Um bom exercício para seu aprendizado seria repetir o exemplo acima e experimentar os outros sinais. Lembre-se, também podemos usar o **jobspec** em vez de PIDs. Processos, como arquivos, têm proprietários, e você deve ser o proprietário de um processo (ou o superuser), a fim de enviar sinais com o **kill**.

Além da lista de sinais acima, que são mais frequentemente usados com kill, existem outros sinais frequentemente utilizados pelo sistema. Você não tem controle sobre isto, mas pode observá-los. Abaixo está uma lista de outros sinais comuns:

- **3** - QUIT. Abandone o processo.
- **11** - SEGV. Violação da segmentação. Perdas de sincronia com swap podem produzir este sinal.
- **20** - TSTP. Manda o processo parar, mas o programa pode decidir não parar. É o equivalente ao Ctrl-Z.
- **28** - WINCH. Ordena o redimensionamento da janela.

Você pode conseguir uma lista completa de sinais com a opção -l como pode ver abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830969/untitled-1-06.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830969/untitled-1-06.png)

Também é possível enviar sinais para vários processos correspondentes a um programa especificado ou usando o comando **killall**.  Aqui está a sintaxe:

**Killall [-u user] [-signal] name …**

Para demonstrar, vamos iniciar um par de instâncias do programa xlogo e depois terminá-los:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830970/untitled-1-07.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830970/untitled-1-07.png)

Lembre-se, como com kill, você deve ter privilégios de superusuário para enviar sinais para processos que não lhe pertencem.

### Desligando o sistema

O processo de encerramento do sistema envolve o encerramento ordenado de todos os processos do sistema, assim como executar algumas tarefas vitais do housekeeping (limpeza de casa), como o sincronismo de todos os sistemas de arquivos montados, antes que o sistema seja totalmente desligado. Existem quatro comandos que podem executar esta função. Eles são: **halt, poweroff, reboot e shutdown.** Os três primeiros são bastante autoexplicativos e geralmente são usados sem qualquer opção, por exemplo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830971/untitled-1-08.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830971/untitled-1-08.png)

O comando shutdown é um pouco mais interessante. Com ele, podemos especificar qual dasações devem ser executadas (parar, desligar ou reiniciar), e podemos fornecer um tempo de atraso para o shutdown. Na maioria das vezes é usado como abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830972/untitled-1-09.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830972/untitled-1-09.png)

Para interromper o sistema (desligando o computador), ou como este:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830973/untitled-1-10.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830973/untitled-1-10.png)

Para reiniciar o sistema. O atraso pode ser especificado de várias maneiras. Ver o manual do shutdown para mais detalhes. Uma vez que o comando shutdown é executado, uma mensagem broadcast é enviada para todos os usuários conectados avisando-os do evento iminente.

Sobre o monitoramento de processos, procure experimentar outros programas como **dstree, vmstat, xload e tload.**

### Conclusão

Atualmente os sistemas operacionais apresentam um mecanismo para gerenciar múltiplos processos. O Linux fornece um conjunto de ferramentas para este fim. Dado que o Linux é sistema operacional para servidores mais implantado do mundo, isso faz muito sentido. No entanto, ao contrário de alguns outros sistemas, o Linux baseia-se principalmente em ferramentas de linha de comando para gerenciamento de processos. Embora existam ferramentas de processo gráficas para Linux, as ferramentas de linha de comando são muito mais leves e rápidas. Embora as ferramentas GUI possam parecer bonitas, muitas vezes criam mais carga no sistema, mascarando os resultados reais do estado e performance do sistema.