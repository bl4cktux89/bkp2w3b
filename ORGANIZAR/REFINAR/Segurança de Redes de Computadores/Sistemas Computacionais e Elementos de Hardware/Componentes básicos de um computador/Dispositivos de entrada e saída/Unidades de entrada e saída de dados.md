[![](https://ampli-images.s3.amazonaws.com/production/65f8bb1d-3966-4081-91f6-c08bf67477c9/original)](https://ampli-images.s3.amazonaws.com/production/65f8bb1d-3966-4081-91f6-c08bf67477c9/original)

Como você já viu anteriormente, os computadores atuais são baseados na Arquitetura Von Neumann, que prevê a capacidade de uma máquina digital armazenar na memória dados e instruções, em formato binário, necessários para a execução de uma tarefa. A CPU – Unidade Central de Processamento – busca  estes dados e instruções na memória e executa o processamento, e o resultado deste processamento é disponibilizado na memória. (FÁVERO, 2011).

Como também já foi visto, nesta arquitetura de computadores estão previstas também as unidades de entrada e saída de dados. Como você já deve ter visto, estas unidades são compostas por diversos dispositivos e podem ser divididos em (SOUZA FILHO, 2014):

- **Dispositivos de Entrada** – onde podemos inserir/entrar com dados no computador. Exemplo: teclado, mouse, telas sensíveis ao toque (_touch screen_).
- **Dispositivos de Saída** – onde os dados podem ser visualizados. – Exemplo:

telas e impressoras.

- **Dispositivos de Entrada/Saída** – são dispositivos que podem enviar e receber dados, como o disco rígido, pendrives, as conexões de internet via cabo e _wifi_, monitores e telas _touch screen_, entre outros (FONSECA, 2007).

Existem diversos dispositivos de entrada e saída que também são chamados de periféricos. A cada dia surgem novos equipamentos que fazem a entrada e saída de dados. Segundo Velloso (2014), os elementos de um computador que garantem a ligação do processador com o mundo externo constituem um sistema de entrada e saída, onde temos:

- Barramentos.
- Interfaces.
- Periféricos – dispositivos de entrada e saída (VELLOSO, 2014).

Um processador manipula dados executando ações com o objetivo de obter resultados. São ações comuns à execução de operações aritméticas simples, tais como: somar, subtrair, multiplicar e dividir; operações lógicas e, também, as operações de movimentação de dados entre a CPU e a memória. Os componentes do processador são interligados pelos barramentos que permitem esta movimentação de dados entre a CPU e a memória (MONTEIRO, 2007). Ainda segundo Monteiro, um barramento é o caminho por onde trafegam todas as informações de um computador. Existem três tipos principais de barramentos:

- Barramento de dados.
- Barramento de endereços.
- Barramento de controle.

O conjunto destes três barramentos compõe um Modelo de Barramento de Sistema, conforme a figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/93616ec8-409a-4d02-b057-5f42edc17a4a/original)](https://ampli-images.s3.amazonaws.com/production/93616ec8-409a-4d02-b057-5f42edc17a4a/original)

Modelo de barramento de sistema. Fonte: Souza Filho (2014); Monteiro (2007).

É preciso que você reforce o entendimento sobre os barramentos, pois eles desempenham uma função direta na entrada e saída de dados e, também, sobre o processamento desses dados e o retorno dos resultados deste processamento. Relembrando:

**Barramento de dados** - Este barramento interliga a CPU à memória, e vice-versa, para a transferência das informações que serão processadas. Ele determina diretamente o desempenho do sistema, pois quanto maior o número de vias de comunicação, maior o número de bits transferidos e, consequentemente, maior a rapidez. Os primeiros PCs possuíam barramento de 8 vias. Atualmente, dependendo do processador, este número de vias pode ser de 32, 64 e até de 128 vias (FÁVERO, 2011).

**Barramento de endereços** - Interliga a CPU à memória fazendo seu endereçamento e tem o número de vias correspondente à tecnologia de _bits_ do processador, ou seja, nos computadores mais modernos, 32 _bits_ ou 64 _bits_, permitindo endereçar até quatro GB (_Gigabytes_) de memória em processadores 32 _bits_ e cerca de 16 PB (_Petabytes_) no caso de processadores 64 bits (SOUZA FILHO, 2014).

**Barramento de controle** - Interliga na CPU a Unidade de Controle aos componentes e dispositivos de um computador, componentes de entrada e saída, memórias auxiliares e de armazenamento, entre outros. (MONTEIRO, 2007).

Como visto, o barramento de controle faz a comunicação entre os periféricos de entrada e saída com a CPU do computador. Durante o processamento de um programa, cada instrução é levada à CPU a partir da memória, junto aos dados necessários para executá-la. A saída do processamento é retornada à memória e enviada a um dispositivo, como um monitor de vídeo. A comunicação entre a CPU, a memória e os dispositivos de E / S é feita sempre pelos barramentos (SOUZA FILHO, 2014).

Existem muitas diferenças de características entre os diversos periféricos de E/S, por exemplo, a velocidade de transferência de um teclado ou de um mouse é muito menor do que a velocidade de um HD. Por este motivo, foram criados novos tipos de barramentos, com taxas de transferência de bits diferentes. Existem, atualmente, diferentes tipos de barramentos adotados pelos fabricantes destes dispositivos, onde podemos citar:

- **Barramento Local**: funciona na mesma velocidade do clock (relógio) do processador. Em geral, interliga o processador aos dispositivos com maior velocidade, memória cache e memória principal.
- **Barramento de Sistema**: adotado por alguns fabricantes, faz com que o barramento local faça a ligação entre o processador e a memória cache, e esta memória cache se interliga com a memória principal (RAM). Dessa forma não acontece acesso direto do processador à memória principal. Um circuito integrado auxiliar é usado para sincronizar o acesso entre a memória cache e a RAM, chamado de ponte e mais conhecido como “Chipset”.
- **Barramento de expansão**: também chamado de barramento de entrada e de saída (E/S), é responsável por interligar os diversos dispositivos de E/S aos demais componentes do computador, tais como: monitor de vídeo, impressoras, CD/DVD. Neste caso, também, é usado um chipset para cada dispositivo poder se conectar ao barramento do sistema, estes chipsets (pontes) sincronizam as diferentes velocidades dos barramentos. (FÁVERO, 2011).

[![](https://ampli-images.s3.amazonaws.com/production/2e50e4fe-31e7-4a49-a349-a1ff2a6ac888/original)](https://ampli-images.s3.amazonaws.com/production/2e50e4fe-31e7-4a49-a349-a1ff2a6ac888/original)

Exemplos de barramentos utilizados atualmente. Fonte: Monteiro (2007)

**🔁 Assimile**

Os três principais tipos de barramento de um computador são:

- Barramento de dados.
- Barramento de endereços.
- Barramento de controle.

Além deles, existem, atualmente, diferentes tipos de barramentos adotados pelos fabricantes destes dispositivos, onde podemos citar:

- Barramento local.
- Barramento de sistema.
- Barramento de expansão.