### Introdução

Muitas vezes, as nossas aplicações na web ou dentro das redes locais parecem lentas. E costumamos a atribuir essa lentidão a rede ou ao servidor da aplicação. Mas na verdade, a lentidão, em termos de camadas do modelo TCP/IP, pode estar relacionada com as camadas de enlace, internet e a camada de transporte tanto do cliente quanto do servidor. Este é um assunto complexo, que requer grande atenção por parte dos administradores de rede.

Em termos práticos, a lentidão que pode ocorre nas nossas aplicações por conta do congestionamento. A rede pode ter sido mal projetada para suportar a carga, ou seja, o número de pacotes enviados é maior do que a capacidade da rede.

### Congestionamento na rede

No dia a dia, já nos deparamos com o problema do congestionamento. Ele ocorre basicamente porque existe a espera. Em qualquer sistema que envolva a espera. Imagine que você tenha que ir ao banco, conforme ilustrado na figura abaixo. A capacidade do banco é de atender três clientes simultaneamente, mais do que isso, já começa a surgir a espera e, consequentemente, começa o crescimento da fila (Forouzan, B. A, 2010).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363521/28977.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363521/28977.png)

Conceito de fila

O **congestionamento em rede** ocorre, fundamentalmente, devido as filas (buffers) que os roteadores e comutadores possuem. Essas filas retém os pacotes antes e depois do processamento. Suponha, por exemplo, que um roteador um roteador receba pacotes em sua interface. O processo de receber o pacote em sua fila de entrada e coloca-lo na fila de saída ocorrerá em três fases, de acordo com a figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/6/1/1806170/40349.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/6/1/1806170/40349.png)

Fonte: Forouzan, B. A, 2010

1. O pacote chega na interface do roteador e é colocado na fila de espera para ser verificado.  
2.  
O roteador retira o pacote quando ele chega na frente da fila e baseado no endereço IP de destino consulta sua tabela de roteamento para determinar o melhor caminho.  
3.  
O pacote é colocado na fila de saída e aguarda a sua vez para ser enviado.

Se a velocidade de chega dos pacotes for maior do que de processamento, ocorrerá a fila. O mesmo ocorrerá quando a velocidade de saída dos pacotes for menor do que a velocidade de processamento.

### Congestionamento Cliente/Servidor

Durante as transmissões de dados, as aplicações de rede alocam recursos (buffers) tanto no cliente quanto no servidor e utilizam o mecanismo de janela deslizante controlar o seu tamanho. **O receptor é que controla o tamanho da janela** para evita que ele fique sobrecarregado durante a recepção dos dados**.** A janela pode ser aberta, fechada ou reduzida.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258860/14793.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258860/14793.jpg)

Janela de transmissão

### Controle de congestionamento do protocolo TCP

O TCP utiliza o controle de congestionamento para evitar ou amenizar o congestionamento da rede utilizando para tanto, o espaço disponível no buffer do receptor (_**rwnd**_) e também pelo nível de congestionamento da rede (_**cwnd**_). **O Emissor, portanto, possui duas informações para determinar o tamanho da janela real. O real tamanho é o menor tamanho entre os dois** (Forouzan, B. A, 2010)**.**

**Tamanho real da janela = mínimo (rwnd, cwnd)**

**Exemplo 1:** Qual é o valor da janela receptora (_**rwnd**_) para um host A, se o receptor, o host B, tiver um tamanho de buffer igual 10.000 bytes e desse, 2.000 bytes recebidos e ainda não processados?

**Resposta:** O valor de _**rwnd = 10.000 – 2.000 = 8.000.**_ O host B pode receber até 8000 bytes antes que seu buffer estoure. O host B anunciará esse valor para o host A no próximo segmento transmitido.

**Exemplo 2:** Qual o tamanho da janela do host A se o valor da janela receptora (_**rwnd)**_ é 5.000 e o valor da janela de congestionamento (_**cwnd**_) é 3.500 bytes?

**Resposta:** O tamanho da janela é o menor valor entre _**rwnd**_ e _**cwnd, que é 3.500.**_

### Política de Congestionamento do TCP

A política de congestionamento do TCP para lidar com o congestionamento se baseia em três fases: partida lenta, evitar o congestionamento e detecção de congestionamento (Forouzan, B. A, 2010).

- **Partida lenta:** o emissor começa com uma velocidade de transmissão muito lenta**, com a janela de congestionamento (**_**cwnd) igual ao**_ **tamanho** **de segmento máximo (MSS)**. O MSS é determinado é determinado durante a fase de estabelecimento de conexão e vai aumentando de um MSS a cada confirmação. Nessa fase a janela de congestionamento começa lentamente e vai aumentando exponencialmente até atingir um limiar, conforme mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/6/1/1806173/40350.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/6/1/1806173/40350.png)

Fonte: Forouzan, B. A, 2010

A partida lenta não pode continuar indefinidamente, pois existe um limite para interromper essa fase.  O emissor controla uma variável chamada limiar de partida lenta (_**ssthresh**_). Quando o tamanho da janela em bytes atinge esse limiar, a partida lenta termina e se inicia a fase seguinte (**Evitar o congestionamento**).

- **Evitar congestionamento (Aumento aditivo):** Para se evitar o congestionamento durante a fase de partida lenta, diminui-se o crescimento exponencial. A partir desse momento o crescimento é aditivo (é incrementada em 1 unidade) para cada confirmação de segmento até ser detectado o congestionamento. o TCP define para tanto, um algoritmo chamado evitar o congestionamento (**congestion avoidence**), conforme mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/6/1/1806176/40351.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/6/1/1806176/40351.png)

Fonte: Forouzan, B. A, 2010

- **Detecção de congestionamento (diminuição multiplicativa):** Caso ocorra o congestionamento a janela de congestionamento **(**_**cwnd)**_ deve ser diminuída. Todas as vezes que o tempo de um timer se esgota ou quando o emissor recebe três ACKs o emissor deve **diminuir de forma multiplicativa** para evita o congestionamento.

Caso o tempo se esgotou existe uma grande possibilidade de ocorrência de congestionamento. O segmento pode ter sido descartado e não há noticias do segmento. Neste caso, o TCP:

- Ajusta o valor do limiar (_**ssthresh**_) para a metade do tamanho atual da janela.
- Ajusta _**cwnd**_ para o tamanho de um segmento.
- Inicia a fase de partida lenta novamente

Se forem recebidos três ACKs isso é indicativo de um menor congestionamento, o que faz com que o TCP tenha uma reação mais rápida:

- Ajusta o valor do limiar (_**ssthresh**_) para a metade do tamanho da janela atual.
- Ajusta o _**cwnd**_ para o valor do limiar.
- Inicia a fase de evitar congestionamento.

Para exibir esse processo veja a figura a seguir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/6/1/1806177/40352.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/6/1/1806177/40352.png)

Fonte: Forouzan, B. A, 2010