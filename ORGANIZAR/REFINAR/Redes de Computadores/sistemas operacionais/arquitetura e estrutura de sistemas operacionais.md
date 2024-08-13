### Introdução

O sistema operacional é formado por um conjunto de rotinas que oferece serviços aos usuários e às suas aplicações, ou seja, o SO disponibiliza uma grande variedade de atividades que nós usuários podemos solicitar para satisfazer nossas necessidades. Esse variedade de atividades (softwares) são executadas utilizando os hardwares.

A função do núcleo do SO ou Kernel é conectar ambos: software e hardware, permitindo assim uma eficiente comunicação. A estrutura do núcleo, ou seja, a maneira como o código do sistema é organizado e o inter-relacionamento entre seus diversos componentes podem variar conforme a concepção do SO.

**Núcleo do SO (Kernel)**

O núcleo sempre gerencia a execução das rotinas (processos). Segundo Machado (2002, p. 51), as rotinas do sistema são executadas concorrentemente (simultaneamente, ao mesmo tempo), sem uma ordem predefinida, com base em eventos dissociados do tempo (eventos assíncronos). Muitos desses eventos estão relacionados ao hardware e às tarefas internas do próprio SO. Suas principais funções são:

- Tratamento de interrupções e exceções;
- Criação e eliminação de processos e threads;
- Sincronização e comunicação entre processos e threads;
- Escalonamento e controle de processos e threads;
- Gerência de memória;
- Gerência do sistema de arquivos;
- Gerência de dispositivos de E/S;
- Suporte a redes locais e distribuídas;
- Contabilização do uso do sistema;
- Auditoria e segurança do sistema.

Com a multiprogramação, é natural que usuários diferentes utilizem o mesmo recurso computacional (memória e processador, por exemplo). Nesse caso o  sistema operacional tem que garantir a confiabilidade na execução das tarefas e a integridade do próprio sistema operacional. Para garantir essa integridade e segurança existem os modos de acesso ao núcleo do sistema operacional.

**Modos de acesso ao Kernel**

Para que o usuário não comprometa o sistema operacional, alguns mecanismos de proteção ao núcleo são implementados, os quais são conhecidos como modo de acesso. Normalmente, são dois modos:

- Modo usuário: é o que executa as instruções não privilegiadas, tem acesso ao número reduzido de instruções e não oferece risco ao Sistema;
- Modo kernel: é o modo que executa as instruções consideradas privilegiadas. Somente usuários com permissões específicas possuem autorização para manipular no modo kernel.

Essas instruções necessitam de supervisão, pois podem comprometer o sistema, como a atualização de um arquivo em disco, pois se trata de um dispositivo compartilhado e necessita do gerenciamento do sistema operacional.

**Interpretador de comandos (Shell)**

O interpretador de comandos, como o próprio nome sugere, interpreta as solicitações feitas pelo usuário. Segundo Silberschatz, alguns sistemas operacionais incluem o interpretador de comandos no kernel. Outros, como Windows e UNIX, tratam-no como um programa especial que está sendo executado  quando  uma tarefa é iniciada e o usuário faz a solicitação.

Existem basicamente dois tipos:

- Texto: quando as solicitações são feitas por linhas de comando, como o MS- DOS. São commandos específicos e técnicos, parametrizados sob uma rigorosa sintaxe;
- Gráfico: a interface gráfica surgiu na década de 1970, por meio da Xerox. A primeira versão do Windows era baseada em uma interface gráfica, para o sistema operacional MS-DOS. Esse tipo de interpretador de comandos se caracteriza pelas janelas e ícones. O usuário faz sua solicitação utilizando normalmente o mouse. Atualmente, com o desenvolvimento da eletrônica, temos a possibilidade de fazer as solicitações via “touch screen”, ou seja, com toques na tela.

**Chamadas de Sistemas (System Calls)**

O sistema operacional é composto por rotinas. Essas compõem o núcleo do sistema, oferecendo serviços aos usuários e suas aplicações. Todas as funções do núcleo são implementadas por meio de rotinas do sistema que necessariamente possuem em seu código instruções de modo kernel. Dessa forma, o processador deve estar obrigatoriamente em modo kernel, o que exige a inserção de  mecanismos de proteção para garantir a confiabilidade do sistema.

Todo o controle de execução de rotinas do sistema operacional é realizado pelo mecanismo conhecido como system call. Toda vez que uma aplicação desejar chamar uma rotina do sistema operacional, o mecanismo de system call é ativado. O sistema operacional verificará se a aplicação possui privilégios necessários para executar a rotina solicitada. Em caso negativo, o sistema operacional impedirá o desvio para a rotina do sistema, sinalizando ao programa chamador que a operação não é possível.

Se a aplicação possuir o privilégio para chamar a rotina, o sistema  operacional primeiramente salva o conteúdo dos registradores, troca o modo de acesso do processador de usuário para kernel e realiza o desvio para a rotina alterando o registrador PC com o endereço da rotina chamada. Ao terminar a execução da rotina do sistema, o modo de acesso é alterado de kernel para usuário, e também o contexto dos registradores restaurados, para que a aplicação continue a ser executada a partir da instrução que chamou a rotina do sistema.

Os mecanismos de system call e de proteção por hardware devem garantir a segurança e a integridade do sistema. Dessa forma, as aplicações serão impedidas de executarem instruções privilegiadas sem autorização e a supervisão do sistema operacional.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/7/292759/17242.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/7/292759/17242.png)

Fluxo da interação das System Calls.

Fonte: A. S. TANENBAUM. Sistemas Operacionais Modernos. 2. ed. São Paulo: Pearson Prentice Hall, 2005.

**Serviços do SO**

O sistema operacional se prepara para execução de programas e requer um conjunto de serviços e funções úteis ao usuário. São eles:

- Interface do usuário: atualmente a interface utilizada aos usuários é a GUI (Interface Gráfica com o Usuário), composta por janelas, com dispositivo de apontamentos de E/S, menus e teclado para entrada de texto;
- Execução de programa: o sistema precisa carregar um programa para executá-lo, e o programa precisa encerrar sua execução;
- Operações de E/S: o usuário não consegue controlar os dispositivos de E/S diretamente e necessita que o sistema operacional proporcione meios para realizar essas tarefas;
- Manipulação do sistema de arquivos: é necessário ler, gravar e renomear os arquivos e diretórios, sistemas de pesquisa por meio de nomes ou algum atributo da propriedade (extensão, data criação, aplicativo);
- Comunicações: em algumas situações os processos necessitam trocar informações que estão em um mesmo computador ou não. Essa comunicação pode ser implementada por meio da memória compartilhada ou troca de mensagens, em que o pacote de informações é movido entre processos do sistema operacional;
- Detecção de erros: o sistema operacional precisa estar preparado para os possíveis erros. Eles podem ocorrer na CPU (Unidade Central de Processamento), na memória, nos dispositivos de E/S e no programa do usuário. Para cada tipo de erro, o sistema operacional deve ter uma ação adequada para resolvê-lo.

As funções citadas a seguir são para garantir a eficiência do sistema operacional:

- Alocação de recursos: com a multiprogramação, alguns recursos podem ser solicitados simultaneamente. O sistema operacional precisa alocar recursos a cada um deles. É necessário conhecer a tarefa para que se possa adequar o melhor uso de CPU, dispositivos de E/S e memória;
- Contabilidade: os contadores normalmente são destinados para pesquisadores, com o intuito de descobrir quais são os usuários e quanto utilizam dos recursos, com o objetivo de configuração e melhoria do sistema;
- Proteção e segurança: quando existem diversos usuários fazendo uso do mesmo sistema, há a necessidade da proteção e a não interferência entre processos. A proteção permite a garantia de controle de todo acesso aos recursos do sistema, iniciando-se com a identificação dos usuários, normalmente por meio de senhas.

Com a evolução dos computadores, o gerenciamento que o SO desenvolvia complicou, se tornou mais complexo pois, haviam as possibilidades de multiprocessamentos com time sharing. Para que esse suporte fosse feito da maneira mais eficiente possível, foram desenvolvidas no núcleo, 3 tipos de arquiteturas:

- Sistema Monolítico;
- Sistema em Camadas;
- Sistema Microkernel.

**Sistema Monolítico**

Segundo Machado, o sistema monolítico pode ser comparado com uma aplicação formada por vários módulos que são compilados separadamente, e depois linkados, formando um grande e único programa executável, em que os módulos podem interagir livremente, por exemplo: MS-DOS e os primeiros sistemas Unix.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/8/292859/17243.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/8/292859/17243.png)

Sistema Monolítico.

Fonte: F. B. MACHADO; MAIA, L. P. Arquitetura de Sistemas Operacionais. 2. ed. São Paulo: LTC, 2002.

**Sistemas em Camadas**

Nessa arquitetura com o sistema dividido em camadas sobrepostas, cada  uma recebe um conjunto de funções que podem ser utilizadas apenas em camadas superiores ou inferiores.

Vantagem: isola as funções do sistema operacional, facilitando sua manutenção e depuração, e também criar uma hierarquia de níveis  de modo de acesso, protegendo as camadas mais internas.

Desvantagem: desempenho comprometido, pois a camada só pode se comunicar com a camada acima ou com a camada abaixo.

Atualmente a maioria das versões do Unix e o Windows, da Microsoft, estão baseados nesse modelo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/8/292879/17245.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/8/292879/17245.png)

Sistema em Camadas.

Fonte: F. B. MACHADO; MAIA, L. P. Arquitetura de Sistemas Operacionais. 2. ed. São Paulo: LTC, 2002.

Numa visão diferente das camadas:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/0/8/320817/17246.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/0/8/320817/17246.png)

Sistema em Camadas.

Fonte: F. B. MACHADO; MAIA, L. P. Arquitetura de Sistemas Operacionais. 2. ed. São Paulo: LTC, 2002.

**Microkernel (Cliente Servidor: Client Server)**

Nesse modelo, o núcleo é menor e o mais simples possível, os sistemas são oferecidos por meio de processos, em que cada um é responsável por oferecer um conjunto específico de funções. Dessa forma, se um serviço parar o sistema, não fica comprometido, por exemplo: em um sistema microkernel existem os servidores – arquivos, impressão e internet. Se, por algum motivo, o servidor de internet parar, o serviço cessa, mas a rede não.

A aplicação que faz a solicitação é denominada cliente e o processo que responde à solicitação é chamado de servidor. Para que essa comunicação seja realizada, é utilizado o sistema de troca de mensagem. A principal função do núcleo é realizar a comunicação, ou seja, a troca de mensagens entre cliente e servidor.

Segundo Machado, esse conceito surgiu com o sistema operacional Mach, na década de 1980, na Universidade Carnegie-Mellon. O núcleo do sistema Mach oferece basicamente quatro serviços: gerência de processos, gerência de memória, comunicação por troca de mensagens e operações de E/S, todos em modo usuário.

Os servidores podem executar em modo usuário e não têm acesso direto a alguns componentes do sistema, apenas o núcleo, que é o responsável pela comunicação entre clientes e servidores, executa em modo kernel.

Como os serviços se comunicam por meio de troca de mensagens, não há problema se as tarefas forem executadas em um único processador. Dessa forma essa arquitetura permite sistemas com múltiplos processadores (fortemente acoplado) ou sistema distribuído (fracamente acoplado).

Vantagens:

- Permite acrescentar novos servidores à medida que o numero de clientes aumenta;
- Permite isolar as funções do sistema, por diversos processos servidores pequenos e dedicados, tornando o núcleo menor, mais fácil de depurar e, consequentemente, aumentando a confiabilidade;
- Manutenção mais fácil, pois, ao parar o processo, não precisa interromper toda a rede.

Desvantagens:

- Implementação: dividir o kernel em diversos processos requer alto conhecimento em sistemas operacionais;
- Mudança constante no modo de acesso de usuário para kernel, envolvendo muitas interrupções.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/0/8/320818/17263.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/0/8/320818/17263.png)

Sistema Cliente/Servidor (Client Server).

Fonte: F. B. MACHADO; MAIA, L. P. Arquitetura de Sistemas Operacionais. 2. ed. São Paulo: LTC, 2002.

**Máquina Virtual (Virtual Machine)**

Segundo Machado (2007, p. 60), um sistema computacional é formado por vários níveis, em que cada camada de nível mais baixo é o hardware. Acima dessa camada, encontra-se o sistema operacional que oferece suporte para as aplicações. O modelo de máquina virtual, ou virtual machine (VM), cria um nível intermediário entre o hardware. Esse nível cria diversas máquinas virtuais independentes, no qual cada uma oferece uma cópia virtual do hardware, incluindo os modos de acesso, interrupções, dispositivos de E/S.

Cada máquina virtual é independente. É possível que cada VM tenha seu próprio sistema operacional e que seus usuários executem suas aplicações como se todo computador estivesse dedicado a cada um deles. Na década de 1960, a IBM implementou esse modelo no sistema VM/370, permitindo que aplicações batch, originadas de antigos sistemas OS/360, e aplicações de tempo compartilhado pudessem conviver na mesma máquina, de forma transparente a seus usuários e aplicações.