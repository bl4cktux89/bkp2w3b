### Introdução

Atualmente a capacidade de processamento de aplicações web é uma da maior preocupação das empresas. As transações online e os serviços da web são cada vez mais necessários para garantir os SLAs entre as organizações, sendo assim cada vez mais a medição do desempenho de suas aplicações é necessária.

A medição de desempenho também se torna um índice importante para o planejamento da capacidade dos sistemas, pois a própria rede fornece dados a respeito de sua funcionalidade que, se modelados de forma correta, trazem uma melhor análise sua e planejamento.

Segundo Menascé (2002), a principal fonte de informação é o conjunto de medições de desempenho coletadas de diferentes pontos de teste, cuidadosamente escolhidos para observar e monitorar o ambiente de estudo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/6/302666/20539.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/6/302666/20539.png)

Redes Heterogêneas

### Monitoramento da infraestrutura

O monitoramento da rede, segundo Almeida (2002) está totalmente associado ao seu gerenciamento, devemos perceber que cada vez mais as redes são complexas e heterogêneas, com muitos pontos para se analisar (TANENBAUM, 2003).

1. **Vários tipos de redes**
2. **Vários sistemas operacionais**
3. **Vários tipos de hardware**
4. **Várias linguagens de programação**

Citamos três aspectos importantes a respeito do monitoramento:

1. **O que será monitorado:** definição do que vai ser monitorado e como serão obtidos os dados e Informações do recurso.
2. **Quais ferramentas serão utilizadas:** o que conseguiremos coletar e de que maneira essa coleta será feita.
3. **Onde serão aplicadas as informações coletadas:** definição de como as informações coletadas serão utilizadas.

A coleta de informações de uma rede para análise do desempenho, pode ser feita de duas formas:

1. **Passiva:** esse método mede a performance da rede por meio do monitoramento da taxa de chegada de pacotes no sistema. Não utiliza nenhum recurso da rede e, assim, não interfere em seu desempenho. Na transmissão não devemos monitorar apenas uma das pontas envolvidas, pois isso não dará precisão no resultado final. É necessário entender a transação como um todo, conhecendo a origem dos dados transmitidos.
2. **Ativa:** esse método consiste no envio de pacotes coordenados para a rede, na monitoração das respostas desses pacotes e na sua devida coleta. Por exemplo o comando ping do protocolo ICMP (Internet Control Message Protocol) é uma ferramenta para medição (KUROSE, 2006). Trabalhando com esse comando na rede, por meio de envios regulares de pacotes, conseguimos informações do tipo:
    - **Alcançabilidade:** é medida pela diferença do número de pacotes enviados e recebidos pela estação de medição.
    - **Tempos de resposta - RTT**: o tempo que um bit leva para trafegar de uma extremidade do meio e voltar.
    - **Latência:** é o tempo que um bit leva para chegar ao seu destino.
    - **Perda de pacotes:** é a ocorrência de um ou mais pacotes, que navegam por meio de uma rede de comunicações, não atingindo o seu destino.

Deve-se observar que a monitoração ativa, quando em excesso pode prejudicar a rede, os pacotes de testes enviados na rede podem saturá-la caso existam enlaces com pouca largura de banda, além de afetar as aplicações existentes no servidor de monitorado ou na própria rede.

### Melhores práticas para um desempenho satisfatório

Para conseguirmos um desempenho satisfatório para uma infraestrutura aplicada a servidores web, devemos seguir alguns passos importantes, como definir a banda necessária para um serviço.  Um provisionamento de banda é muitíssimo importante conforme Almeida (2002), pois determina a capacidade que se deve fornecer aos enlaces da rede, em uma determinada topologia, para atingir um determinado desempenho fim a fim.

Para adequar-se às exigências de desempenho da aplicação entre dois terminais de rede, deve-se levar em conta os seguintes aspectos:

**Modelos de demanda de tráfego entre terminais de rede:** modelos precisarão ser especificados tanto no nível da aplicação, quanto no nível de pacote (por exemplo, pacotes sendo gerados em aplicações em andamento).

**Exigências de desempenho definidas:** Por exemplo, a exigência de desempenho para suportar tráfego sensível ao atraso, como uma aplicação interativa de áudio/vídeo. Pode ser que a probabilidade de atraso fim a fim sofrido pelas mensagens da aplicação seja maior que o limite máximo tolerável de atraso, degradando a qualidade da aplicação. Determinar a correta carga de trabalho usando técnicas para descobrir um custo mínimo de alocação de banda, resultará na garantia da qualidade dos serviços prestados aos usuários.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/4/9/304990/18389.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/4/9/304990/18389.jpg)

Desempenho dos canais

### Medição de desempenho

A estrutura de medição deverá oferecer uma série de dados importantes observados nas três funções de gerenciamento de desempenho:

- Detecção de problemas operacionais.
- Ajuste de desempenho.
- Planejamento de capacidade.

É importante ainda observar a medição de toda a infraestrutura de rede que deverá ser feito em partes (respeitando toda a heterogeneidade da rede) e a medição da aplicação que deve ser feita em todo seu ciclo.

Toda a arquitetura de medição do desempenho deve ser implementada para analisar os aspectos que envolvem a aplicação. Algumas métricas são importantes e serão mostradas a seguir.

- **Medições do lado do usuário:** essas medições são implementadas para se conhecer e monitorar o ambiente dos usuários, o que também afeta o tempo de resposta.
- **Inspeção de tráfego na rede:** são ferramentas implementadas para monitorar e coletar todo o tráfego da rede.
- **Medição de performance dos servidores:** essa métrica é aplicada no próprio sistema operacional, que deve ser capaz de medir o desempenho do servidor em produção
- **Tempo de resposta da aplicação:** geralmente usa-se uma API implementada no próprio código da aplicação para medir o tempo de resposta dos servidores.
- **Análise do fluxo da rede:** ferramentas para coletar medições de atualização dos segmentos da rede, a fim de analisar o seu desempenho.
- **Medição de WAN:** ferramentas implementadas para analisar todo o tráfego de entrada e saída da rede WAN.

Para todas essas métricas utilizamos dois itens imprescindíveis:

1. Os pontos de testes, ou seja, os locais onde a medição é realizada.
2. Os agentes de medição, que realizam as medições ou coleta de dados.

### Representação do processo de medição

O processo de medição é composto por quatro itens importantes que compõem essa metodologia, os quais são descritos abaixo:

1. **Especificação das medições:** decidir quais variáveis serão medidas, por exemplo, rede Ethernet. Medições de pacotes e colisões por segundo ou aplicação de streaming. Qual a qualidade do sinal desejada na mídia.
2. **Especificações de pontos de teste:** determinar onde os dados de desempenho serão coletados. Por exemplo, é possível determinar que o ponto de partida deva coletar dados sobre o tráfego que atravessa a LAN onde os servidores web estão localizados.
3. **Instrumentação da coleta de dados:** depois de selecionar as variáveis a serem observadas, devemos distribuir ferramentas de medição para monitorar o sistema e coletar os dados para o uso. Dependendo das medições definidas, pode-se fazer necessária a instalação de várias ferramentas de medição, por diferentes pontos do sistema.
4. **Análise e transformação de dados:** as ferramentas de medição normalmente capturam uma quantidade muito grande de dados bruto, que correspondem a uma observação detalhada do sistema. Esses dados precisam ser analisados e transformados em informações significativas, por exemplo, tamanhos médios, número de acessos, popularidade de arquivos, entre outro.

As medições podem ser efetuadas de três maneiras distintas, dependendo de como o processo de medição foi especificado. Podem ser por eventos , por rastreamento ou por amostragem.

### Medição por evento

Neste tipo de medição gera-se um registro toda vez que ocorre um caso dentro de um conjunto de tipos determinados. Um evento normalmente muda o estado do sistema, especificado por um conjunto de variáveis. Ao ser detectado determinado evento, um código especial chama uma rotina que gera informações, como data, hora, tipo de evento, etc.

### Medição por rastreamento

Essa medição é muito semelhante à anterior, só que gera um registro do evento ocorrido e do estado do sistema no momento. Por exemplo, em vez de só contar erros de transmissão, o rastreamento registraria o estado do sistema com as causas do erro.

### Medição por amostragem

Nesta medição, as informações dos sistemas são coletadas em instantes predefinidos. Em vez de ocorrer por evento, acontecem em um instante predeterminado, especificado no início da sessão de monitoração. Ela provoca impacto no resultado da medição, o que chamamos de overhead. Quanto maiores às amostragens, maiores serão os overheads e menor será a precisão da medição.