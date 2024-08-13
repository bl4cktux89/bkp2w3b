### Introdução

Ao longo do tempo, acompanhando os computadores, os sistemas operacionais evoluíram também. Desde o surgimento da informática, a evolução é constante, pois sempre surgem novos softwares e hardwares, mais potentes e mais adaptados às necessidades dos seres humanos (mais "userfriends").

Essa evolução tem um preço: problemas de gerenciamento generalizado (o SO gerencia todos os softwares e hardware). Os softwares estão cada vez mais complexos, pois antes era apenas “uma rotina” a ser gerenciada, com a evolução passaram a ser várias e executadas ao mesmo tempo, simultaneamente.

Para que o SO garanta a integridade e confiabilidade de cada tarefa solicitada pelo usuário, ele (SO) a trata como um “Processo”, alocando recursos e registradores específicos para cada tarefa. Este tópico visa demonstrar como isso é feito.

### Estrutura do processo

Em um primeiro momento, processo pode ser definido como um “programa em execução”. Em função da evolução, atualmente seu conceito e responsabilidade é bem maior. Pode ser definido como sendo “toda a estrutura necessária para que um programa seja executado (alocação de processador, memória e dispositivos de E/S)”.

Segundo Machado, processo pode ser definido como um “conjunto necessário de informações para que o sistema operacional implemente a concorrência de programas”.

No sistema multiusuário, cada usuário tem seu programa associado a um processo. O usuário tem a impressão de possuir todos os recursos exclusivamente para ele, mas todos os recursos estão sendo compartilhados, inclusive a CPU - Central Processing Unit (Unidade Central de Processamento). Ocorre que o processador executa o programa de um usuário durante um intervalo de tempo e, no instante seguinte, estará processando outro programa. Se houver falta de recursos, o sistema operacional poderá impedir a execução, com sucesso, de um programa.

Um processo é formado por três partes: contexto de hardware, contexto de software e espaço de endereçamento.

**Contexto de Hardware**

Esse contexto armazena o conteúdo dos registradores gerais da CPU - Central Processing Unit (Unidade Central de Processamento), além dos registradores de uso específico, como program counter, stack pointer e registrador de status.

O contexto de hardware é fundamental para a implementação dos sistemas multiprogramáveis, pois, como já discutimos anteriormente, há várias tarefas, mas são executadas simultaneamente, e não ao mesmo tempo. Para que isso seja possível, o sistema operacional trabalha com interrupções junto aos registradores. Vamos exemplificar: o usuário está conectado na internet e ouvindo musica. A sensação é de que ambas as tarefas estão sendo executadas no mesmo instante. O sistema operacional aloca processador apenas para uma, no momento, e reveza essa alocação entre as tarefas. Ao interromper a internet, o sistema operacional salva o registrador, aloca para o outro recurso, no caso, a música, posteriormente retorna a conexão da internet, restaura o registrador e continua a execução de onde houve a interrupção.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/9/296906/17302.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/9/296906/17302.png)

Contexto de Hardware num Processo.

Fonte: MACHADO, F. B.; MAIA, L. P. Arquitetura de Sistemas Operacionais. 2. ed. LTC, 2002.

**Contexto de Software**

Nesse contexto são especificados limites e características dos recursos que podem ser alocados pelo processo (processador, memória, dispositivos de E/S). Muitas dessas características são determinadas no momento da criação do  processo, enquanto outras podem ser alteradas durante sua existência.

É composto por três grupos de informações:

- Identificação;
- Quotas;
- Privilégios.

Identificação: ao ser criado, o processo recebe duas identificações: PID (Process Identification), representado por um número. É por meio dele que o sistema operacional faz o gerenciamento; há também o UID (User Identification), que permite implementar o modelo de segurança, em que apenas os objetos que possuem a mesma UID do usuário podem ser acessados.

Quotas: refere-se aos limites de recursos a serem atribuídos para  a tarefa. Caso não seja suficiente, o processo pode ser executado lentamente, ser interrompido ou não ser executado. Alguns exemplos de quota:

- Número máximo de arquivos abertos simultaneamente;
- Tamanho máximo de memória principal e secundária que o processo pode alocar;
- Número máximo de operações de E/S pendentes;
- Número máximo de processos, subprocessos e threads que podem ser criados.

Privilégios: define ações que um processo pode fazer em relação a ele mesmo, aos demais processos e ao sistema operacional.

**Espaço de Endereçamento**

Ele pertence à área de memória do processo em que instruções e dados do programa  são  armazenados  para  execução.  Cada  processo  possui  seu  próprio espaço de endereçamento, que deve ser devidamente protegido do acesso dos demais processos.

**Bloco de Controle do Processo (Process Control Block - PCB)**

O processo é implementado pelo SO por meio de uma estrutura chamada PCB - Process Control Block (Bloco de Controle de Processos). A partir do PCB o SO mantém todas as informações sobre os processos em execução, ou seja, sobre o contexto de hardware, o contexto de software e o espaço de endereçamento de cada processo.

Os PCBs de todos os processos ativos residem na memória principal, em  uma área exclusiva do sistema operacional. O tamanho dessa área geralmente é limitado por um parâmetro do sistema operacional que permite especificar o número máximo de processos que podem ser suportados simultaneamente pelo sistema.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/9/296908/17303.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/9/296908/17303.png)

PCB - Process Control Block: Bloco de Controle de Processo.

Fonte: MACHADO, F. B.; MAIA, L. P. Arquitetura de Sistemas Operacionais. 2. ed. LTC, 2002.

**Estados dos Processos**

No sistema multiprogramável, um processo não deve alocar exclusivamente a CPU, pois existe o compartilhamento no uso do processador e demais recursos computacionais. Por esse motivo, os processos alteram-se em diferentes “estados” ao longo do seu processamento, em consequência de eventos gerados pelo sistema operacional ou pelo próprio processo.

Um processo em execução pode passar pelos seguintes estados:

- **Novo:** ao ser criado;
- **Pronto:** o processo encontra-se no estado de pronto quando aguarda para ser executado. O sistema operacional é quem determina a ordem e os critérios para que o processo saia do estado de pronto de acordo com o algoritmo de escalonamento;
- **Em execução:** quando o processo está fazendo uso do processador. Os processos se revezam na utilização do processador seguindo uma política de escalonamento determinado pelo sistema operacional;
- **Em espera:** quando o processo aguarda por algum evento externo ou por algum recurso computacional de entrada ou saída para seguir com o seu processamento. Por exemplo, pressionamento de uma tecla, ou o clique em um botão;
- **Encerrado:** quando o processo é finalizado e destruído pelo sistema operacional.

**Mudanças de estado do processo**

Todo processo muda de estado durante sua execuçao e seu ciclo de vida (desde quando é criado até não ser mais processado) em razão  de dois tipos de eventos:

- Criados por ele próprio: eventos voluntários como, por exemplo, a leitura de arquivos para entrada de informações e gravação de informações em arquivos de saída;
- Criados pelo SO: eventos involuntários como uma chamada para execução, previamente escalonada no SO (chamada automática), exemplo: quando você liga seu computador, vários processos entram em execução automáticamente (confira isso acessando a aba “Processos” do “Gerenciador de Tarefas”).

As mudanças de estado que podem acontecer com um processo são:

- **Pronto → Execução:** após a criação de um processo, o sistema operacional coloca em uma lista de processos no estado de pronto, em que aguarda para ser executado. Como já citado anteriormente, cada sistema operacional tem seus próprios critérios;
- **Execução → Espera:** um processo em execução passa para o estado de espera por eventos gerados pelo próprio processo (eventos voluntários), como uma operação de E/S, ou por eventos externos (eventos gerados pelo sistema operacional);
- **Espera → Pronto:** um processo passa no estado de espera para o estado de pronto. A solicitação é atendida ou o recurso que aguarda é concedido. Para sair do estado de espera e passar para o estado de execução, ele obrigatoriamente vai para o estado de pronto, pois o sistema operacional só seleciona processos para execução dos que estiverem no estado de pronto;
- **Execução → Pronto:** um processo em execução passa para o estado de pronto por eventos externos, como por exemplo, se o tempo estimado para execução do processo expirar. Se isso ocorrer, o processo volta para a fila de pronto, em que irá esperar por uma nova oportunidade para continuar seu processamento.

**Criação e eliminação de processos**

Os processos são criados e eliminados por diversas razões. A criação ocorre a partir do momento em que o sistema operacional adiciona um novo PCB (Bloco de Controle de Processos) à sua estrutura e atribui um espaço de endereçamento  na  memória  para  uso.  Após  a  criação  do  PCB, o SO já detecta a existência do processo, sendo assim é possível gerenciar e associar programas ao seu contexto para serem executados.

Para eliminar o processo, todos os recursos associados a ele deverão ser retirados e o PCB deletado pelo sistema operacional.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/0/297038/17304.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/0/297038/17304.png)

Mudanças de Estados de um Processo.

Fonte: MACHADO, F. B.; MAIA, L. P. Arquitetura de Sistemas Operacionais. 2. ed. LTC, 2002.