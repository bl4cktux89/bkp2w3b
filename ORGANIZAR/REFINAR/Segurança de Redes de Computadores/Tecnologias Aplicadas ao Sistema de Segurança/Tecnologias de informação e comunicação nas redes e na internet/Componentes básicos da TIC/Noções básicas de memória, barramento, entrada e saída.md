[![](https://ampli-images.s3.amazonaws.com/production/7d728723-03c6-4972-8aa9-5eec68983f5f/original)](https://ampli-images.s3.amazonaws.com/production/7d728723-03c6-4972-8aa9-5eec68983f5f/original)

Tanto Hennessy e Patterson (2014) quanto Stallings (2010) definem memória como elementos onde são depositadas (temporária ou permanentemente) informações e de nos quais essas informações podem ser recuperadas.

Uma analogia com o mundo real seria um caderno ou um livro. No caderno ou no livro, podemos armazenar informações que podem ser recuperadas. No caso do caderno, as informações podem ser armazenadas temporariamente, pois se as escrevemos com lápis, essas informações podem ser apagadas.

No caso do livro, as informações ali armazenadas estão presentes permanentemente, após a impressão, não podendo ser reescritas. Há várias maneiras de classificarmos as memórias presentes em um computador.

Stallings (2010) oferece, entre outras, a classificação por permanência da informação. Por essa classificação, temos basicamente dois tipos de memória:

**Memória ROM**Do inglês _read only memory_, ou memória apenas para leitura. Trata-se da memória permanente, isto é, uma vez gravada, não é apagada, a não ser em alguns casos especiais, e nunca pelo usuário durante a operação do computador.

Não depende de o computador estar ligado para manter seus valores (depois de desligarmos e ligarmos o computador, as informações gravadas em ROM permanecerão sempre as mesmas). Pode ser dos seguintes subtipos:

- ROM Básica – sua construção é em pastilha de silício, e os dados são “prensados” junto à pastilha em si. Uma vez escritas as instruções, não há como alterá-las nem em regime de manutenção.
- PROM (_Programmable_ ROM) – Refere-se a uma memória ROM um pouco mais maleável: é construída de forma genérica, permitindo que qualquer instrução ou dado seja gravado a posteriori em suas posições. Uma vez gravado (programado) uma instrução ou dado, não há mais como ser alterado.
- EPROM (_Erasable_ PROM) – além de poder ser programada, a EPROM pode ser apagada quando exposta a uma luz ultravioleta. Este tipo de memória é muito usada em laboratório, quando se testam novas configurações para algum componente do computador.
- EEPROM (_Electrically Erasable_ PROM) – além de poder ser programada, pode ser apagada, mas sem a necessidade de uma luz ultravioleta. Este tipo de EPROM pode ser apagado com uso de uma corrente elétrica aplicada a um de seus terminais.

**Memória RAM**Do inglês _random access memory_ (memória de acesso aleatório). Trata-se da memória temporária, na qual as informações (bits “0” e “1”) são armazenadas sob forma de sinais elétricos. Os dados armazenados podem ser apagados ou reescritos de acordo com a necessidade, e só estarão disponíveis enquanto o computador estiver ligado. São dos seguintes subtipos:

- RAM Estática – cada bit é formado por um circuito chamado “flip-flop”, composto por um conjunto de transistores. Uma vez armazenado, o bit fica presente sem a necessidade de outras ações para sua permanência, a não ser a alimentação do circuito. São rápidas, mas ao mesmo tempo mais caras, uma vez que para cada bit são necessários vários transistores.

É usada no cache, isto é, na porção interna do processador que armazena dados e informações a serem usados mais imediatamente.

- RAM Dinâmica – cada bit é formado por um capacitor. Uma vez armazenado, o bit precisa ser “refrescado” de tempos em tempos, uma vez que a carga do capacitor não é permanente, e tende a se deteriorar com o tempo. É mais lenta que a memória estática, mas muito mais barata, pois, ao invés de vários transistores, demanda apenas um capacitor para sua criação.

Há, ainda, as memórias secundárias, isto é, locais de armazenamento permanente, nos quais guardamos arquivos que não estão sendo manipulados pelo processador.

Os HDs (_hard disks_, ou discos rígidos, os _floppy disks_ (ou discos maleáveis) são exemplos desse tipo de armazenamento. Veja na figura a seguir um exemplo de um HD.

[![](https://ampli-images.s3.amazonaws.com/production/2f8cab66-7b04-42e8-8124-164bea00a5f7/original)](https://ampli-images.s3.amazonaws.com/production/2f8cab66-7b04-42e8-8124-164bea00a5f7/original)

Unidade de Disco Rígido Aberta. Fonte: Pixabay.

Os barramentos são os circuitos que permitem a entrada e a saída de dados dos _chips_ (processadores, memórias, periféricos etc.). São sempre de múltiplos de 8 bits e, atualmente, os barramentos mais comuns são de 84 bits, permitindo a transferência de 8 e 8 _bytes_ (sendo que 1 _byte_ tem 8 bits).

______

**💭** **Reflita**Se a memória estática é mais rápida, por que não a utilizamos como toda a memória RAM do Computador? Em outras palavras, por que precisamos recorrer às memórias dinâmicas, mais lentas?