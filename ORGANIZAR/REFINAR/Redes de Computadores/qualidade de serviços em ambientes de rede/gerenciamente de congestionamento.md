**WFQ (**_**Weighted Fair Queuing**_**)**

Procura fornecer uma quantidade diferenciada de serviço a cada classe, num dado período de tempo, atribuindo-lhes pesos diferentes.

A WFQ divide o "_**bandwith**_" através de filas de tráfego baseado em pesos assegura que todo o tráfego é tratado de acordo com as regras, dado seu peso. Exemplo: Considere uma fila para pacotes FTP como uma fila coletiva e uma fila para tráfego de pacotes interativos como uma fila individual. De acordo com o peso das filas, ele assegura que para todos os pacotes da fila coletiva transmitidos, um número igual de pacotes da fila individual seja, também, transmitido. Assim, a WFQ assegura, satisfatoriamente, o tempo de resposta a aplicações críticas, tal como as interativas e aplicações baseadas em transações que são intolerantes a degradações em performance.

Outra característica de funcionamento da WFQ é que ela calcula e assinala o tempo de transmissão de cada pacote. Com base na taxa de transmissão de uma porta de saída, na quantidade de filas, no peso de cada fila e no tamanho de cada pacote de cada fila, é possível calcular o tempo final de chegada de cada pacote. O escalonador seleciona e envia o pacote que possui o menor tempo de chegada que é calculado entre todos os pacotes que estão no início de cada fila, ou seja, em resumo, suporta fluxos com diferentes necessidades de largura de banda, atribuindo a cada fila uma porção da largura de banda.

A WFQ também oferece suporte a pacotes com tamanhos variáveis, provendo uma alocação justa de largura de banda de modo que fluxos com pacotes maiores não aloquem mais banda que fluxos com pacotes menores.

Com base na taxa de bits da porta de saída, no número de filas ativas, na porção da largura de banda alocada para cada fila e no tamanho dos pacotes de cada fila, a disciplina WFQ calcula e atribui um número para cada pacote de entrada que representa a ordem na qual os pacotes devem ser escalonados. O escalonador seleciona e transmite o pacote que possuir o menor número dentre todos os pacotes armazenados nas filas existentes no sistema.

**CB-WFQ (Class-Based WFQ)**

Trata-se de outra ferramenta de gerenciamento de filas (enfileiramento), que pode ser aplicada para quando se necessitar de um uso mínimo de largura de banda para cada fila. Você pode configurar a porcentagem atual da banda, assim como uma contagem de byte. Comparando CB-WFQ com WFQ: o primeiro pode usar os recursos já existentes no segundo para uma determinada fila, porém não poderá manter o mesmo fluxo por todo o tráfego.

O CB-WFQ suporta até 64 filas com o comprimento de cada fila variando com o modelo do roteador usado e a quantidade de memória nele instalado. Todas as filas são configuráveis, porém existe uma, conhecida como class-default, que recebe uma configuração automática.

**LLQ (**_**Low Latency Queuing**_**)**

O LLQ (enfileiramento de baixa latência) demonstra ser o melhor sistema de enfileiramento de baixa latência, justamente por seu nome já dizer isso.

Ele tem uma compreensão simples para sua configuração, assumindo que você realmente entendeu a proposta do CB-WFQ. Não é uma ferramenta separada para tratar enfileiramento, mas sim uma possibilidade simplificada do CB-WFQ aplicada a uma ou mais classes. Exemplo: Se você usa CB-WFQ e usa um comando de prioridade (_**prioriy**_) para habilitar o LLQ em uma das classes, você de fato está utilizando LLQ, que será a classe com o comando de prioridade.

Um exemplo do funcionamento do LLQ pode ser observado na Figura 1:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119236/a08i01_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119236/a08i01_quasar80_100.jpg)

Figura 1: Serviços de fila com LLQ e CBWFQ. Fonte: Odom e Cavanaugh, 2012.

Observando a imagem, é possível notar que o agendador LLQ sempre analisa primeiramente a fila de baixa latência e encaminha o pacote vindo daquela fila.

Com o LLQ, você pode ter o melhor dos dois mundos: tráfego de baixa latência em uma fila e garantia de largura de banda para o tráfego de outra fila.

**Considerações finais**

Dando continuidade a nossa aula anterior, na qual tratamos de marcação e classificação de pacotes, nesta aula abordamos o gerenciamento de congestionamento, mostrando a você, caro aluno, a importância do trabalho dessas ferramentas para uma melhor qualidade de serviços numa rede de computadores.