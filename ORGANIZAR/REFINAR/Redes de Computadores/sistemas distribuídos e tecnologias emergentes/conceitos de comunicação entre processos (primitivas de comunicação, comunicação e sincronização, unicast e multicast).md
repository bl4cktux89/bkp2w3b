Comunicação entre processos está no coração de todo Sistema Distribuído, por isso temos de examinar cuidadosamente os modos pelos quais processos podem trocar informações em máquinas diferentes.

A comunicação em Sistemas Distribuídos é sempre baseada em troca de mensagens de baixo nível, o que se torna mais difícil do que usar primitivas  baseadas em memória compartilhada, como a disponível em plataformas não distribuídas.

Em aplicações distribuídas, a comunicação não segue o padrão restrito desenvolvido nas redes cliente-servidor, por esse motivo é mais adequado pensar em termos de mensagens. Dessa forma, como os recursos de comunicação de uma rede de computadores de baixo nível não são adequados, devido a falta de transparência de distribuição, se torna conveniente adotar um modelo de alto nível de enfileiramento de mensagens, no qual a comunicação ocorra do mesmo modo que em sistemas de correio eletrônico.

Sistemas Distribuídos modernos consistem em milhares ou milhões de processos espalhados por uma rede cuja comunicação não é confiável, como é o caso da Internet. Entretanto, visando diminuir esses problemas, os processos comunicantes têm de obedecer determinadas regras, que são ditadas pelos Protocolos, o que será apresentado nesta aula.

**Protocolos em Camadas**

Como vimos anteriormente, a comunicação entre processos em Sistemas Distribuídos é baseada no envio e recebimento de mensagens, ou seja, quando um processo **A** quer se comunicar com o processo **B**, ele monta uma mensagem em seu próprio espaço de endereçamento, e executa uma Chamada de Sistema ao Sistema Operacional que envia a mensagem até o processo **B**, mas o que parece simples pode se tornar um caos se regras não forem definidas e obedecidas.

Para ficar mais fácil lidar com os vários níveis e questões envolvidos em comunicação, a ISO (International Organization for Standardization) desenvolveu um modelo de referência que identifica os vários níveis envolvidos, os padroniza e indica qual nível executa determinado serviço. Esse modelo é chamada do **MR-OSI** (Open System Interconnection Reference Model).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/5/301504/19892.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/5/301504/19892.png)

Modelo de Referência - OSI

Fonte:

O modelo OSI é projetado para permitir que sistema abertos se comuniquem, usando regras padronizadas que regem o formato, o conteúdo e o significado das mensagens recebidas, sendo essas regras chamadas de **protocolos**.

No modelo OSI a comunicação é dividida em até sete camadas, sendo que cada camada lida com um aspecto específico da comunicação, sendo cada uma dessas camadas gerenciáveis e independentes umas das outras. Entretanto, cada camada fornece uma interface de comunicação com a camada que está acima dela, consistindo em um conjunto de operações que definem o serviço que cada camada está preparada a oferecer aos usuários.

Veja como é dividido o Modelo OSI, incluindo as referências dos protocolos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/6/301648/19893.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/6/301648/19893.png)

Protocolos no Modelo de Referência OSI

Fonte: Figura 4.1 - pag. 70 do Livro Sistemas Distribuídos - Princípios e Paradigmas.

Nos **protocolos orientados a conexão**, antes de trocar dados, o remetente e o receptor estabelecem previamente uma conexão e negociam o tipo de protocolo que usarão, liberando assim a conexão.

Já nos **protocolos sem conexão**, não é necessário estabelecer nada antecipadamente, pois o remetente envia sua mensagem quando estiver pronto, como por exemplo: uma caixa de correio.

O que se deve ressaltar é que cada camada tem seu próprio protocolo que podem ser alterados independentemente um do outro, à medida que a tecnologia avança, sem que os outros sejam afetados.

O conjunto de protocolos utilizados em determinado sistema é denominado de **suíte de protocolos** ou **pilha de protocolos.**

**Protocolos de níveis mais baixos**

As três camadas mais baixas da pilha de protocolos OSI, implementam as funções básicas que abrangem uma rede de computadores.

A **camada física** se ocupa de transmitir os bits, bem como trata da padronização das interfaces elétricas, mecânicas e de sinalização.

Na **camada de Enlace**, a preocupação se volta para a detecção e correção de erros que possam surgir durante a comunicação. Ela agrupa os bits em unidades, chamadas de quadro, e providencia para que cada quadro seja corretamente recebido.

No terceiro caso, do protocolo de nível mais baixo, está a **camada de rede**, que se preocupa em receber a mensagem do remetente e enviá-la até o  receptor, seja por um caminho mais curto ou por um caminho com alguns saltos. Esse percurso é chamado de **roteamento**. O protocolo de rede que cuida da tarefa de rotear o pacote do remetente até o receptor é, atualmente, o **IP** (Internet Protocol - Protocolo de Internet).

**Protocolo de Transporte**

A **camada de transporte** forma a última parte da pilha de protocolos de rede, uma vez que implementa todos os serviços não fornecidos na interface da camada de rede, mas que são necessários para construir aplicações de rede, transformando a rede subjacente em algo que um desenvolvedor de aplicação pode usar.

Ao receber uma mensagem da camada de aplicação, a camada de transporte a desmembra em porções pequenas dando um número de sequência a cada pedaço e em seguida envia-os.

O protocolo de transporte da Internet é chamado de **TCP** (Transmission Control Protocol - Protocolo de Controle de Transmissão), cuja combinação com o IP, Protocolo TCP/IP, é usado como o padrão para comunicação em rede.

Outros protocolos são suportados nessa camada, tais como,  o **UDP** (Protocolo Universal de Datagramas), que é utilizado por usuários que não precisam de um protocolo orientado à conexão; e o **RTP** (Protocolo de Transporte em Tempo Real), que especifica formatos de pacotes para dados em tempo real, mas que não fornece a garantia de entrega desses pacotes.

**Protocolos de Níveis mais Altos**

A **camada de Sessão** é uma versão melhorada da camada de transporte, pois ela proporciona controle de diálogo para monitorar qual é a parte que está falando no momento considerado e fornece facilidades de sincronização.

A **camada de apresentação** se preocupa com o significado dos bits, uma vez que as mensagens consistem em informações estruturadas como nomes de pessoas, endereços, quantias, etc., o que  facilita a comunicação entre máquinas que tenham representações internas diferentes.

A camada de aplicação é o repositório  para todas as aplicações e protocolos que não se ajustam a uma das camadas subjacentes. Os protocolos dessa camada são: **FTP** (Protocolo de Transferência de Arquivos), responsável por transferir arquivos entre uma máquina cliente e uma máquina servidora; o **HTTP** (Protocolo de Transferência de Hipertexto) que é projetado para gerenciar e manipular a transferência de páginas Web.

**Comunicação Orientada a Mensagem**

Chamadas de procedimento remoto e invocações de objeto remoto contribuem para ocultar a comunicação em Sistemas Distribuídos, uma vez que aprimoram a transparência de acesso.

Como nenhum desses mecanismos é sempre adequado, são necessários serviços alternativos de comunicação, que no nosso caso é a troca de mensagens.

Muitos Sistemas Distribuídos são construídos diretamente em cima do modelo simples orientado a mensagem, oferecido pela camada de transporte.

A padronização da interface da camada de transporte foi alvo de especial atenção para permitir que programadores usem todo o seu conjunto de protocolos por meio de um conjunto simples de primitivas, sendo que essas interfaces padronizadas facilitam portar uma aplicação para máquinas diferentes.

Como exemplo dessa padronização temos a **interface Sockets**, que é um terminal de comunicação para o qual uma aplicação pode escrever dados que devem ser enviados pela rede subjacente e do qual podem ler dados que chegam, ou seja, uma comunicação de dupla direção que liga dois programas executando em rede.

Um soquete forma um abstração sobre o terminal de comunicação que é usado pelo Sistema Operacional local, para um protocolo de transporte específico. Quando se usa a interface Sockets, o fechamento de uma conexão é simétrico e é conseguido ao se fazer com que ambos, cliente e servidor, chamem uma primitiva _**close.**_

Vejamos na figura abaixo, como é o padrão geral seguido por um cliente e servidor para uma comunicação orientada a conexão, usando a interface Sockets:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/6/301689/19894.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/6/301689/19894.png)

Comunicação orientada a Objeto - Interface Sockets

Fonte: Figura 4.14 - pag. 86 do Livro Sistemas Distribuídos - Princípios e Paradigmas.

Com o advento dos multicomputadores de alto desempenho, desenvolvedores começaram a procurar primitivas orientadas a mensagem que lhes permitisse escrever com facilidade aplicações de alta eficiência.

Assim, as primitivas deveriam estar em um nível conveniente de abstração, para facilitar o desenvolvimento da aplicação, e que sua implementação incorresse em uma sobrecarga mínima. Isso os soquetes não poderiam atender.

A necessidade de ser independente de hardware e de plataforma resultou na definição de um padrão para troca de mensagens, chamado de **MPI** (Interface de Passagem de Parâmetros), que foi projetado para aplicações paralelas e que considera que falhas sérias, como queda de processo ou partições de rede, fossem fatais e requeressem recuperação automática.

A MPI adota a premissa de que a comunicação ocorre dentro de um grupo conhecido de processos, onde cada grupo recebe um identificador, que identifica a fonte ou o destinatário de uma mensagem e é usado no lugar de um endereço de nível de transporte.

**Comunicação persistente Orientada a Mensagem**

Conhecido como  **MOM** (Middleware Orientado a Mensagem), é uma classe importante de serviços de Middleware, conhecidos como **sistema de enfileiramento de mensagem**, que proporcionam suporte extensivo para comunicação assíncrona persistente e que oferecem capacidade de armazenamento de médio prazo para mensagens, sem exigir que o remetente ou o receptor estejam ativos durante a transmissão da mensagem.

A ideia que fundamenta um sistema de enfileiramento de mensagens é que aplicações se comuniquem inserindo mensagens em filas específicas, que são repassadas por uma série de servidores de comunicação e, entregues ao destinatário, mesmo que não esteja em funcionamento quando a mensagem foi enviada.

Vejamos na figura abaixo quatro combinações em relação ao modo de execução do remetente e receptor:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/6/301693/19896.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/6/301693/19896.png)

Combinações para comunicações - Sistema de Enfileiramento.

Fonte: Figura 4.15 - pag. 88 do Livro Sistemas Distribuídos - Princípios e Paradigmas.

Na figura (a), remetente e receptor, executam durante toda a transmissão de uma mensagem.

Na Figura (b), somente o remetente está em execução, enquanto o receptor está passivo, em um estado ao qual a entrega da mensagem não é possível, mas mesmo assim, o remetente pode enviar mensagens.

Na figura (c), temos a combinação de um remetente passivo e um receptor em execução, onde o receptor pode ler mensagens que lhe foram enviadas, mas não é necessário que seus respectivos remetentes estejam em execução.

E na última, a figura (d), vemos a situação em que o sistema está armazenando e transmitindo mensagens, mesmo que o remetente e o receptor estão passivos.

**Comunicação Multicasting**

Um ponto importante da comunicação em Sistemas Distribuídos é o suporte para enviar dados a vários receptores, o que caracteriza a comunicação multicasting.

A ideia básica do multicasting é que os nós se organizem em uma rede de sobreposição que é usada para disseminar informações para seus membros, sendo que as conexões entre os nós na rede de sobreposição podem cruzar vários enlaces físicos, e por isso, o roteamento de mensagens dentro da rede de sobreposição podem não ser bom.

A questão importante é como deve ser projetada a construção de uma rede de sobreposição. Uma das possibilidades é que os nós podem se organizar diretamente em uma árvore, o que significa que há um único caminho de sobreposição entre cada par de nós.

A outra, seria os nós se organizarem em uma rede de malha no qual cada nó terá vários vizinhos, o que disponibilizaria vários caminhos entre cada par de nó.

A diferença entre essas possibilidades é que a última oferece mais robustez, ou seja, se uma conexão for interrompida porque um nó falhou, ainda assim haverá uma oportunidade para propagar informações sem ter de reorganizar toda a rede de sobreposição.

Veja abaixo um exemplo de uma rede de sobreposição:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/7/301778/19898.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/7/301778/19898.png)

Relação entre enlaces em uma rede de sobreposição

Fonte: Figura 4.26 - pag. 101 do Livro Sistemas Distribuídos - Princípios e Paradigmas.

A qualidade de uma árvore multicast de nível de aplicação é medida por três parâmetros de medição diferentes: **estresse de enlace, alongamentos e custo da árvore.**

O **estresse de enlace** é definido por enlace e conta quantas vezes um pacote cruza o mesmo enlace. Caso um estresse de enlace seja maior que 1, resulta no fato de que embora em um nível lógico um pacote  possa ser  repassado ao longo de duas conexões diferentes, parte dessas conexões pode corresponder ao mesmo enlace físico.

O **alongamento** mede a razão entre dois nós na sobreposição e o atraso que esses dois nós sofreriam na rede subjacente. Observe na figura acima: se adotarmos a rota **B --> Rb --> Ra --> Rc** até chegar em **C**, teríamos um custo total de 59 unidades. Mas se utilizássemos a rede subjacente, e rotear as mensagens por **B--> Rb --> Rd --> Rc** até chegar em **C**, teríamos um custo total de 47 unidades.

Por fim temos o **custo da árvore**, que é um parâmetro de medição global, relacionado com a minimização dos custos agregados de enlaces, ou seja, se o custo de um enlace for considerado atraso entre dois nós finais, então otimizar o custo da árvore se resume em achar a _**spanning tree**_ mínima na qual o tempo total para disseminar informações para todos os nós é mínimo.

Obs.: _**spanning tree**_ é um protocolo para equipamentos de rede que permite resolver problemas de loop em redes comutadas cuja topologia introduza anéis nas ligações, auxiliando na melhor performance da rede.