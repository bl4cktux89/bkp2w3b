Máquinas com múltiplo fluxo de instruções e múltiplo fluxo de dados ainda se dividem nos chamados **multiprocessadores**, com memória compartilhada e arquitetura de rede de interconexão baseada em barramento e, os **multicomputadores** sem memória compartilhada e arquitetura de rede do tipo comutada.

Um sistema é dito multiprocessado quando um ou mais processadores tem por   objetivo concluir uma tarefa em comum, permitindo assim que vários programas sejam  executados em paralelo ou que tenham duas ou mais instruções executadas em paralelo.

Os multiprocessadores cuja conexão é feita com barramento de dados de alta velocidade, são também chamados de **fortemente acoplados** e os multicomputadores interligados via rede ou outros dispositivos comutados em baixa velocidade, é também chamado de **fracamente acoplados**.

**Sistemas fracamente acoplados**

São aqueles onde temos as estações independentes ligadas por rede local, e dependem dessa rede para distribuir a tarefa de processamento entre as CPU’s de estações diferentes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294037/17227.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294037/17227.png)

Sistema Fracamente Acoplado.

Cada sistema por trabalhar de forma independente, possui seu próprio sistema operacional e gerencia seus próprios recursos, como CPU, memória e dispositivos de entrada/saída.

Os sistemas fracamente acoplados caracterizam-se por possuir dois ou mais sistemas computacionais conectados através de linhas de comunicação.

Em função destas características, os sistemas fracamente acoplados também são conhecidos como **multicomputadores**.

Neste modelo, os nodos têm baixo grau de interação e interagem quando necessário. Se a rede local cai, aplicações individuais em cada estação podem continuar.

**Sistema fortemente acoplado**

Podemos classificar como um sistema fortemente acoplado, os sistemas no qual existe um paralelismo no processamento causando um aumento da capacidade de processamento.

É aquele onde o software integra fortemente cada nodo (um ponto de interconexão) da rede, independente da função do equipamento representado por ele.

Nos sistemas fortemente acoplados existem vários processadores compartilhando uma única memória física e os periféricos e que são gerenciados por apenas um Sistema Operacional.

Em função desta característica, os sistemas fortemente acoplados também são conhecidos como **multiprocessadores**.

Os Sistemas Fortemente Acoplados podem ser divididos em **Simétrico** (SMP - Symmetric Multiprocessors), que é uma forma de paralelismo, onde um grupo de processadores trabalha em conjunto compartilhando uma única memória através de um único barramento. Isso torna possível que qualquer processador execute parte do processo; e **Assimétrico**, cuja característica é possuir um processador primário (Mestre), responsável pelo controle dos demais processadores (Escravos) e pela execução do Sistema Operacional. Neste tipo de organização somente um processador pode executar serviços do Sistema Operacional (O Mestre), sendo que se um processador do tipo Escravo necessitar realizar qualquer operação, deverá solicitar primeiro ao processador Mestre.

Neste tipo de sistema se a interligação dos processadores for interrompida, a aplicação também será descontinuada.

**SISTEMAS OPERACIONAIS DE REDE**

Um sistema operacional de redes é um conjunto de funções básicas, e de uso geral que ampliam os recursos dos Sistemas Operacionais, tornando transparente o uso de recursos compartilhados da rede.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294038/17229.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294038/17229.png)

Compartilhamento de recursos da rede.

Em um Sistema Operacional de Redes, os equipamentos estão interligados entre si, mas cada equipamento possui seu próprio Sistema Operacional, seu hardware e software e se utilizam de seus próprios recursos de processamento, que possibilitam ao sistema ter acesso a outros componentes da rede, compartilhando seus recursos.

São sistemas classificados como fracamente acoplados onde seus “hosts” trabalham de forma independente um do outro.

Nesse tipo de sistema, um computador utiliza seu Sistema Operacional Local para interagir com o Sistema Operacional de Redes, possibilitando o uso dos recursos fornecidos pela própria rede, tão fácil quanto o uso dos recursos existentes na máquina local.

Para que isso seja possível, o Sistema Operacional de Redes coloca _**“**__**um redirecionador**__**”**_ entre o aplicativo do cliente e o Sistema Operacional Local, facilitando as buscas dos recursos na própria rede.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/0/297033/18537.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/0/297033/18537.png)

Redirecionador

Estes sistemas são altamente flexíveis, pois são independentes da tecnologia, porém a comunicação através de troca de mensagens reduz o desempenho do processamento global. Apesar da possibilidade de agregar grandes quantidades de recursos, isto leva a grande quantidade de comunicação que afeta não apenas o desempenho, mas também a segurança dos dados.

Os tipos de arquiteturas usadas para Sistema Operacional de Redes são:

**Peer-to-peer:**

Peer to Peer significa, par a par, o que quer dizer que os computadores da rede estão todos interligados em uma cadeia descentralizada, onde cada um possui funções equivalentes não havendo uma hierarquia entre eles. Todos os usuários são clientes e servidores, funcionando, assim, de forma totalmente independente e livre da existência de um servidor central, mas que se utilizam de um Sistema Operacional Local.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/7/296756/17231.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/7/296756/17231.png)

Arquitetura peer-to-peer.

**Cliente / servidor:**

Arquitetura que se utiliza de uma máquina servidora que não executa aplicativos locais, mas que fornece serviços aos seus clientes em uma rede de computadores.

A característica do modelo cliente-servidor descreve a relação de programas numa aplicação. O servidor fornece uma função ou serviço a um ou mais clientes, que iniciam os pedidos de serviço.

Serviços do tipo troca de e-mail, acesso à internet ou acesso a um banco de dados, são construídos com base no modelo cliente-servidor.

Encontramos nesta arquitetura os **Servidores Dedicados**, responsáveis por manter dados centralizados oferecendo seus serviços, exclusivos, aos seus clientes. E também, os **Servidores não-dedicados**, onde o servidor oferece mais de um serviço a sua rede.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294039/17232.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294039/17232.png)

Exemplo de um Servidor Dedicado.

**SISTEMAS OPERACIONAIS DISTRIBUÍDOS**

Sistemas Distribuídos não são diferentes dos sistemas em rede, são sistemas fracamente acoplados interconectados por uma rede de comunicação, porém apresentam menor autonomia entre seus componentes, de forma que possa interagir o suficiente para dar a impressão de um único sistema e coeso.

Os sistemas distribuídos precisam que seus componentes possuam a mesma tecnologia para obter a ilusão de um sistema único

Do ponto de vista de um processador específico, os demais processadores e respectivos recursos são remotos, enquanto seus recursos são locais.

O propósito de um sistema distribuído é fornecer um ambiente eficiente para o compartilhamento de recursos remotos.

Um dos principais desafios para sistemas geograficamente dispersos refere-se à questão de sincronização de sistemas cooperativos que trabalham de maneira concorrente.

A definição de Tanenbaum simplifica a visão de Sistema Distribuído:

“Sistema Distribuído é um conjunto de computadores independentes (autônomos) que se apresenta a seus usuários (pessoas ou programas) como um sistema único e coerente”

Tanenbaum, 2007

()

Para um conjunto de componentes autônomos aparentarem ser um único sistema deve-se ter componentes que colaboram entre si. Isto significa que precisarão executar as tarefas de maneira cooperativa, estando sujeitos aos mesmos problemas de sincronização.

Assim, de modo geral, sistemas com múltiplos processadores ou com múltiplos fluxos de controle (_**Threads**_) são tratados como Sistemas Distribuídos.

O principal objetivo de um Sistema Distribuído é proporcionar aos usuários e aplicações uma facilidade no acesso aos recursos remotos e ao compartilhamento desses recursos, de maneira eficiente e controlada.

Apesar das características que tornam os Sistemas Distribuídos vantajosos para a maior parte das aplicações, seu funcionamento adequado depende de um sistema de gerenciamento único e eficiente o que, em muitos casos, é extremamente difícil de ser obtido.

Há diversas razões e diversos motivos para se querer compartilhar recursos, mas a mais importante diz respeito à economia. É muito mais econômico permitir que uma impressora seja compartilhada por diversos equipamentos, do que ter de adquirir uma para cada usuário.

Seguindo a mesma linha de raciocínio, faz sentido compartilhar servidores, sistemas de armazenamento e outros tipos de periféricos.