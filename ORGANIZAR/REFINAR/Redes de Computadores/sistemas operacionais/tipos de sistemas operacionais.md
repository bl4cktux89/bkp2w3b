### Introdução

Quando falamos em sistemas operacionais, o que vem à mente são os que utilizamos diariamente nos nossos PCs (em casa ou no trabalho) ou nos celulares, mas os SO vão muito além disso. Desde o início os SO evoluíram muito (conjuntamente com os computadores), pois tiveram que ser adaptados às novas tecnologias que foram surgindo. A história mostra uma união sólida entre a eletrônica e a informática. Esta segunda sempre se estribando na primeira e evoluindo junto.

Vamos abordar neste tópico os vários conceitos dos SO, pois atualmente os SO possuem um pouco de cada tipo e são considerados híbridos.

**Monoprogramável / Monotarefa**

Com o surgimento dos primeiros computadores, vieram os sistemas monoprogramável / monotarefa e sua característica principal é a execução apenas de uma tarefa por vez. Para outro processo ser executado, deve-se aguardar o término total do processo anterior, igual ao conceito de "fila única de atendimento". Exemplo: há a necessidade se processar 3 programas: B31, Z65 e J88. Deve ser definida uma ordem de execução, ou seja, qual será o primeiro, qual será o segundo e o terceiro. Digamos que a sequência é a mesma citada acima. Dessa forma, o programa B31 é chamado para a execução e somente ao término deste poderá ser chamado o Z65. Ao término da execução do programa Z65 será chamado o programa J88. Um por vez, sem exceção.

Desvantagem: esse tipo de SO desperdiçava a capacidade de processamento dos computadores, pois enquanto o programa aguardava por um evento I/O (uma impressão de relatório, por exemplo), o processador ficava ocioso e a memória era subutilizada, caso o programa não a utilizasse totalmente.

Vantagem: não havia concorrência em nenhum recurso do computador: não havia fila de impressão, não havia o estado de “wait” (aguardando) um acesso ao HD.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/3/314399/17142.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/3/314399/17142.png)

Monotarefa: execução de uma tarefa por vez.

Fonte:

**Multiprogramável / Multitarefa**

Exatamente por causa da subutilização de recursos na monoprogramação e o elevado custo desse sistema, desenvolveram-se os sistemas multiprogramáveis / multitarefa, em que a principal característica é o compartilhamento de recursos, proporcionando dessa forma a redução de custos. Nesse sistema, enquanto uma tarefa aguarda por um evento I/O, outra tarefa pode ser executada, fazendo uso do processador e da memória. Um exemplo é o atendimento da próxima pessoa de uma fila enquanto a pessoa que está sendo atendida aguarda alguma providência.

Desvantagem: é a implementação, pois o Sistema Operacional precisa gerenciar os recursos compartilhados.

Esses sistemas dividem-se em: Sistemas Batch, Tempo Compartilhado e Tempo Real. Dependendo da implementação, o sistema operacional pode gerenciar um ou mais tipos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/4/314401/17143.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/4/314401/17143.png)

Multitarefa: vários processamentos sendo executados simultaneamente.

Fonte:

**Sistemas Batch**

É chamado de “processamento em lote”, pois as informações são armazenadas em arquivos específicos e, num posterior momento são processadas. Um exemplo disso é quando vamos a algum local e somos atendidos por um atendente que faz uma atualização das nossas informações no sistema (imagine que há muitas atualizações a serem feitas no sistema). É comum ouvirmos: “Pronto! Eu já atualizei aqui no Sistema, mas só aparecerá na tela amanhã”. Essa situação é exatamente o caso de uma atualização que depende de um processamento batch. Os dados atualizados pelo atendente ficam gravados num arquivo. Esse arquivo será utilizado somente a noite (ou madrugada) no processamento batch. Após o processamento batch as informações são atualizadas no sistema e, caso forem pesquisadas no dia seguinte, estarão OK, conforme o atendente informou.

Nesses sistemas a principal característica é a pouca intervenção do usuário.

Na década de 1960, quando começaram a ser implementados, os programas eram submetidos a cartões perfurados, produzindo uma saída em disco ou fita. Vemos aplicações em batch em cálculos numéricos, compilações, ordenações, backups.

Vantagem: otimização da utilização da capacidade de processamento, pois, deixa-se para processor “depois” o que não precisa ser processado imediatamente.

Desvantagem: caso ocorra um erro no processamento, há o comprometimento da disponibilização das informações atualizadas no “dia seguinte”, podem atrasar.

**Sistemas de Tempo Compartilhado**

Também conhecido como “Time sharing”, consegue executar diversas tarefas ao mesmo tempo (simultaneamente), pois existe a divisão do tempo do processador em pequenos intervalos, denominados fatias de tempo.

O processador dedica uma fatia de tempo a cada processamento das tarefas e, caso a tarefa não termine durante a fatia a ela determinada, há uma interrupção e ela volta para a fila de escalonamento, aguardando novamente sua vez. Isso ocorre ciclicamente, até o final das execuções das tarefas.

Um exemplo: temos 4 tarefas a serem executadas, 3 dessas tarefas tem 3 passos, apenas uma delas tem 4 passos a serem processados:

- Tarefa A1: passos A1.1 , A1.2 , A1.3;
- Tarefa H3: passos H3.1 , H3.2 , H3.3;
- Tarefa Y6: passos Y6.1 , Y6.2 , Y6.3 , Y6.4;
- Tarefa X7: passos X7.1 , X7.2 , X7.3.

Todas as 4 tarefas (A1, H3, Y6 e X7) são chamadas para processamento. O processador atende:

- O primeiro passo da A1 que é o passo A1.1;
- O primeiro passo da H3 que é o passo H3.1;
- O primeiro passo da Y6 que é o passo Y6.1;
- O primeiro passo da X7 que é o passo X7.1.

Como nenhuma tarefa terminou, o processador atende então:

- O segundo passo da A1 que é o passo A1.2;
- O segundo passo da H3 que é o passo H3.2;
- O segundo passo da Y6 que é o passo Y6.2;
- O segundo passo da X7 que é o passo X7.2.

Ainda nenhuma tarefa terminou, o processador atende então:

- O terceiro passo da A1 que é o passo A1.3 e a tarefa A1 termina;
- O terceiro passo da H3 que é o passo H3.3 e a tarefa H3 termina;
- O terceiro passo da Y6 que é o passo Y6.3;
- O terceiro passo da X7 que é o passo X7.3 e a tarefa X7 termina.

Perceba que já foram executadas (processadas) as tarefas A1, H3 e X7, essas finalizaram porém, como ainda falta um passo da tarefa Y6, o processador atende:

- O quarto passo da Y6 que é o passo Y6.4 e a tarefa Y6 termina.

Ao término de todas as execuções das tarefas, o processador fica disponível, aguardando o processamento de novas tarefas.

Percebeu como ele atende “uma por vez”, mas processa um pedaço de cada uma? Esse é o conceito de “Compartilhamento de Tempo” (Time sharing).

Diferente do sistema batch, esse tipo de sistema operacional permite a interação do usuário. Dessa maneira, os terminais possuem teclado, vídeo e mouse.

Vantagem: otimização da capacidade de processamento do computador.

Desvantagem: concorrência de recursos, pode haver fila para liberação de dispositivos de E/S (I/O).

**Sistema de Tempo Real**

Sistemas de tempo real (Real Time) tem como característica o tempo rígido no processamento das informações, ou seja, as informações são atualizadas no sistema no mesmo instante.

Seu objetivo e proporcionar o máximo de confiabilidade com o mínimo de intervenção humana. Se houver atraso no processamento, os danos podem ser irreparáveis. Não existe fatia de tempo, o programa é executado enquanto não surgir outro com maior prioridade.

Encontramos esse sistema em: sistemas de controles de veículos espaciais e aviões, torres de controle de aeroportos, robótica, controles industriais, refinaria de petróleo, usinas nucleares e também no controle do metrô.

Vantagens: as informações sempre estão atualizadas.

Desvantagens: custos, pois envolve uma série de estratégias de contingência que, em função da necessidade das informações estarem atualizadas e disponíveis.

**Sistemas de Computadores Pessoais**

Os sistemas operacionais de computadores pessoais são considerados “maiores”. Isso por causa da necessidade de satisfação do usuário final. Cada um possui uma necessidade específica, como: computação gráfica, games, filmes, música. O sistema operacional precisa estar preparado para atender a todas essas demandas.

Desvantagem: falta de segurança, pois caso o usuário erre, pode ocorrer o comprometimento das informações.

Vantagem: o usuário tem livre acesso a todas as informações e dispositivos disponíveis, pode ordenar e decidir o que fazer primeiro.

**Sistemas com múltiplos processadores**

Sistemas com múltiplos processadores caracterizam-se por possuir dois ou mais processadores trabalhando em perfeita comunicação.

Esse sistema possui duas classificações:

1. Fortemente acoplado;
2. Fracamente acoplado.

Para diferenciá-los é necessário conhecer a forma de comunicação entre os processadores, o grau de compartilhamento de memória e dispositivos I/O.

**1 - Sistemas fortemente acoplados**

Vários processadores, compartilhando barramento, memória, clock, I/O e gerenciados por apenas um sistema operacional.

Classificam-se em:

1.1 - Fortemente acoplado assimétrico;

1.2 - Fortemente acoplado simétrico.

1.1 - Sistemas fortemente acoplados assimétrico

Os sistemas fortemente acoplados assimétricos caracterizam-se por possuir hierarquia entre os processadores, existindo o mestre e o escravo, em que o sistema operacional reside apenas no processador-mestre, ele gerencia e distribui as solicitações para os processadores escravo. A principal desvantagem dessa arquitetura é se o mestre falhar, pois dessa forma toda a estrutura é comprometida.

1.2 Sistemas fortemente acoplados simétrico

Os sistemas fortemente acoplados simétricos se diferem do assimétrico, pois não possuem hierarquia entre os processadores. Cada um deles possui uma cópia do sistema operacional e é ele o responsável pelo gerenciamento. Caso algum processador seja paralisado por qualquer motivo, a estrutura não é comprometida, pois o sistema operacional fará o balanceamento de carga, ou seja, distribuirá a tarefa entre os processadores ativos.

**2 - Sistemas fracamente acoplados**

Sua principal característica é possuir dois ou mais sistemas conectados por meio de linhas de comunicação. Cada sistema é independente, possui seu próprio sistema operacional e gerencia seus recursos. Baseado na integração dos hots da rede, podem-se dividir em:

2.1 - Sistema operacional de rede;

2.2 - Sistema operacional distribuído.

2.1 - Sistema operacional de rede

Cada sistema, também chamado de host ou nó, possui seus próprios  recursos de hardware, como processadores, memória e dispositivos de E/S. Os nós são totalmente independentes dos demais, sendo interconectados por uma rede de comunicação de dados formando uma rede de computadores.

Os sistemas operacionais podem ser diferentes, mas, para se comunicarem, os nós precisam ter o mesmo protocolo de rede. Na internet, por exemplo, é o protocolo da família TCP/IP (Transmission Control Protocol / Internet Protocol).

2.2 - Sistema operacional distribuído

Segundo Machado, um sistema distribuído é um conjunto de sistemas autônomos, interconectados por uma rede de comunicação e que funciona como se fosse um sistema fortemente acoplado. Cada componente de um sistema distribuído possui seus próprios recursos, como processadores, memória principal, dispositivos de E/S, sistema operacional e espaço de endereçamento. Os tipos de sistemas operacionais que compõem o sistema distribuído não precisam ser necessariamente homogêneos.

Nesses sistemas é possível que uma aplicação seja dividida em diferentes partes, e podem se comunicar por meio de linhas de comunicação, podendo cada parte ser executada em qualquer processador de qualquer sistema.