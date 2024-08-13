### Introdução

Três invenções foram o marco da impressionante evolução dos sistemas de telecomunicações até os dias de hoje, em 1844, Samuel Morse inventou o telégrafo, em 1876, Graham Bell inventou o telefone; em 1895 Marconi, o rádio. Podemos dizer que as primeiras redes, foram as centrais telefônicas, **Agner Krarup Erlang** matemático dinamarquês**,** estudando uma melhor forma de otimizar os recursos de uma central telefônica, analisando o número de chamadas telefônicas que poderiam ser feitas simultaneamente aos operadores das estações de comutação, acaba desenvolvendo uma distribuição de probabilidades que hoje é conhecida como distinção de Erlang. Utilizada muito na telefonia em cálculo de recursos para PABX (Private Automatic Branch eXchange) e atualmente em soluções de comunicação IP, VoIP, dimensionamento de Call Center, etc (MENASCÉ,2002).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/9/9/319966/20125.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/9/9/319966/20125.jpg)

Private Automatic Branch eXchange

### Características

O pensamento que motivou o estudo de Erlang, foi analisar as chamadas telefônicas de entrada numa central e qual seria os recursos necessários. Raciocinou que se as chamadas chegam no sistema com uma taxa de Poisson, os tempos de serviço são mutuamente independentes e exponenciais, e todas as chamadas que chegam e encontram a linha ocupada, isto é, obtém um sinal de ocupado são descartadas, de modo que, este modelo tem sempre sido, de fato, de muita utilidade no projeto de telecomunicações (CHEUNG et al., 2002).

**O Modelo M/Em/c, representa:**

- Chegadas seguem Poisson.
- Atendimento segue a Distribuição Erlang de grau m.

**O dimensionamento de equipamentos leva em conta os seguintes indicadores:**

- Fornece ao cliente o menor tempo em fila.
- Um sistema de menor custo e máxima capacidade de produção.
- **Para um dado TF desejado, o modelo M/Em/c necessita de uma menor quantidade de servidores que o modelo M/M/c.** Segundo Prado (2014), isso significa que no modelo M/M/c há um superdimensionamento de servidores, mas vale ressaltar que para valores pequenos da taxa de utilização ? a diferença entre os dois modelos é menos significativa.

**O Modelo M/Em/1, apresenta:**

- Distribuição Densidade Erlang.
- Para m=1, possui o mesmo formato que a Função Exponencial Negativa.
- À medida que m cresce, a distribuição tende para a normal.
- Se m tende para infinito. A distribuição tende para uma constante (TA), ou seja, quanto maior m mais constante se torna o tempo de atendimento. Como mostra Prado (2014), o fator m é um medidor de ordem ou desordem do tempo de atendimento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/5/345594/25598.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/5/345594/25598.jpg)

Evolução da telefonia

### Aplicações

Dimensionamento do número de troncos de um Call Center.

**DIMENSIONAMENTO BÁSICO**

1. Previsão do volume de contatos a serem realizados/recebidos, durante determinado período de tempo
2. Definição dos canais de acesso e roteamento/fluxo dos contatos
3. Definição da Qualidade e nível de serviço, além de tempos máximos de espera e % aceitável de abandono e de bloqueio (ocupado)
4. Cálculo inicial da quantidade de troncos
5. Cálculo inicial da quantidade de atendentes por horário - quantidade de PAs.

**DIMENSIONAMENTO AVANÇADO**

1. Inclusão de Operações com Telemarketing Ativo e outros tipos de contato (email, chat etc)
2. Análise de Tipos de Turnos e Jornadas (4h, 6h, etc)
3. Cálculo de Custos
4. Escalas de trabalho, horas extras
5. Estudo de Roteamento avançado (URA, menus de opção a cliente, transbordos etc)
6. Simulação de Cenários alternativos

### Conceito básicos sobre tráfego telefônico

**Tráfego Telefônico**

O tráfego é definido como o número de mensagens em um circuito durante um determinado período de tempo, a carga de tráfego é a razão entre chegadas de chamadas em um período de tempo especificado e o tempo médio decorrido para atender cada chamada durante esse período e é medida em erlangs. Essas unidades de medida são baseadas em AHT (Average Hold Time),ou seja, o tempo médio de espera. Para calcular o AHT basta dividir o tempo total de todas as chamadas em um período especificado, pelo número de chamadas naquele período (CHEUNG et al., 2002) como mostra o exemplo a seguir:

**3976s (tempo total de chegadas das chamadas) / 23 (total de chamadas no período) = 172.87 segundos por chamada = AHT de 172.87 segundos.**

Um erlang corresponde a 3.600 segundos de chamadas no mesmo circuito, ou seja, a carga de tráfego suficiente para manter um circuito ocupado por uma hora. Tráfego em erlangs é o produto do número de tempos de chamadas AHT dividido por 3.600, como mostra o exemplo a seguir:

**(23 total de chamadas no período * 172.87 AHT)/3600 = 1.104 erlangs**

**Grade de Serviços**

GoS (Grade of Service) é definida como a probabilidade de bloqueio de chamadas ao tentar tomar os circuitos, ou seja, qual a probabilidade do circuito estar ocupado quando for solicitado, por exemplo a probabilidade de ligar para um Call Center e todos os circuitos estarem ocupados, em tabelas de valores de Erlang são também conhecidas como probabilidade de perda da ligação.

### Análise dos modelos de tráfego utilizando Erlang B - Aplicação no tráfego telefônico

**Erlang B -**  A fórmula de Erlang B é utilizada no estudo de sistemas com perdas e utilizada para dimensionamento de troncos telefônicos e qualquer outro equipamento que receba tráfego.

O modelo de tráfego **Erlang B** é baseado nas seguintes hipóteses:

- Um número infinito de fontes
- Padrão de chegada de tráfego aleatório
- Chamadas bloqueadas retiradas
- Tempos de espera distribuídos exponencialmente

O modelo Erlang B é utilizado quando as chamadas bloqueadas são roteadas novamente, nunca voltando ao grupo do tronco original. Esse modelo presume um padrão de chamada de chegada aleatório. O chamador faz somente uma tentativa; se a chamada for bloqueada, será roteada novamente. O modelo Erlang B é comumente utilizado para grupos de tronco de primeira tentativa, no qual não é necessário considerar a taxa de novas tentativas porque os chamadores são roteados novamente ou espera-se uma taxa de bloqueio muito baixa.

### Exemplo de cálculo de tráfego utilizando Erlang B

É necessário reprojetar os grupos do tronco de interurbano de saída, que atualmente apresentam algum bloqueio durante o horário de pico. Os relatórios do switch indicam que o grupo do tronco oferece 17 erlangs de tráfego durante o horário de pico. Para ter baixo nível de bloqueio, é preciso desenhar para menos de 1 por cento o bloqueio.Para executar este exercício foi consultada a tabela de valores de Erlang B, extraída do site: [**www.**](http://ccs.dogpile.com/ClickHandler.ashx?encp=ld%3d20161121%26app%3d1%26c%3dinfo.dogpl%26s%3dDogpile%26rc%3dinfo.dogpl%26dc%3d%26euip%3d189.46.224.44%26pvaid%3d1d4a04760086462a946f20c036b088ec%26dt%3dDesktop%26sid%3d1830193568.1958333499020.1479726836%26vid%3d1830193568.1958333499020.1476282568.15%26fcoi%3d417%26fcop%3dtopnav%26fct.uid%3de2b2bd2439e84f539964b0cdc4301795%26fpid%3d2%26en%3d0WEFU%252fZhSoTF%252fFm%252bpLeuVl4UPZzISdzyg%252baGYj7N8ISb7M1aTnzzgA%253d%253d%26ru%3dhttp%253a%252f%252fwww.erlang.com.br%252fdownload%252fErlangB.PDF%26coi%3d1494%26npp%3d1%26p%3d0%26pp%3d0%26mid%3d9%26ep%3d1%26du%3dwww.erlang.com.br%252fdownload%252fErlangB.PDF%26hash%3d7D880C831443E1C4A80DADD80FB20D51&ap=1&cop=main-title)[**erlang**](http://ccs.dogpile.com/ClickHandler.ashx?encp=ld%3d20161121%26app%3d1%26c%3dinfo.dogpl%26s%3dDogpile%26rc%3dinfo.dogpl%26dc%3d%26euip%3d189.46.224.44%26pvaid%3d1d4a04760086462a946f20c036b088ec%26dt%3dDesktop%26sid%3d1830193568.1958333499020.1479726836%26vid%3d1830193568.1958333499020.1476282568.15%26fcoi%3d417%26fcop%3dtopnav%26fct.uid%3de2b2bd2439e84f539964b0cdc4301795%26fpid%3d2%26en%3d0WEFU%252fZhSoTF%252fFm%252bpLeuVl4UPZzISdzyg%252baGYj7N8ISb7M1aTnzzgA%253d%253d%26ru%3dhttp%253a%252f%252fwww.erlang.com.br%252fdownload%252fErlangB.PDF%26coi%3d1494%26npp%3d1%26p%3d0%26pp%3d0%26mid%3d9%26ep%3d1%26du%3dwww.erlang.com.br%252fdownload%252fErlangB.PDF%26hash%3d7D880C831443E1C4A80DADD80FB20D51&ap=1&cop=main-title)[**.com.br/download/ErlangB.PDF**](http://ccs.dogpile.com/ClickHandler.ashx?encp=ld%3d20161121%26app%3d1%26c%3dinfo.dogpl%26s%3dDogpile%26rc%3dinfo.dogpl%26dc%3d%26euip%3d189.46.224.44%26pvaid%3d1d4a04760086462a946f20c036b088ec%26dt%3dDesktop%26sid%3d1830193568.1958333499020.1479726836%26vid%3d1830193568.1958333499020.1476282568.15%26fcoi%3d417%26fcop%3dtopnav%26fct.uid%3de2b2bd2439e84f539964b0cdc4301795%26fpid%3d2%26en%3d0WEFU%252fZhSoTF%252fFm%252bpLeuVl4UPZzISdzyg%252baGYj7N8ISb7M1aTnzzgA%253d%253d%26ru%3dhttp%253a%252f%252fwww.erlang.com.br%252fdownload%252fErlangB.PDF%26coi%3d1494%26npp%3d1%26p%3d0%26pp%3d0%26mid%3d9%26ep%3d1%26du%3dwww.erlang.com.br%252fdownload%252fErlangB.PDF%26hash%3d7D880C831443E1C4A80DADD80FB20D51&ap=1&cop=main-title), na figura abaixo é apresentada parte da tabela.

**Solução:**

Observando as Tabelas de Erlang B, verifica-se que para 17 erlangs de tráfego e uma GoS (Perda) de 1% (na tabela está com círculo amarelo), o valor seria de 26 circuitos, como o exercício pede menor que 1 % , verifica-se que para o valor de 0,6% temos 16,9 erlang (na tabela está com círculo vermelho) são necessários 27 circuitos para atender a essa carga de tráfego.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/6/2/356262/29756.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/6/2/356262/29756.png)

Fonte: www.erlang.com.br/download/ErlangB.PDF

### Análise dos modelos de tráfego utilizando Erlang B prolongado - Aplicação no tráfego telefônico

O modelo de tráfego Erlang B Prolongado é baseado nas seguintes hipóteses:

- Um número infinito de fontes
- Padrão de chegada de tráfego aleatório
- Chamadas bloqueadas retiradas
- Tempos de espera distribuídos exponencialmente

O modelo de Erlang B Prolongado foi projetado para considerar as chamadas com novas tentativas a uma certa taxa. Esse modelo presume um padrão de chamada de chegada aleatório, no qual os chamadores bloqueados fazem várias tentativas para completar as chamadas e não é permitido sobrefluxo. O modelo Erlang B Prolongado é comumente utilizado em grupos de troncos independentes com uma possibilidade de nova tentativa (por exemplo, um pool de modems).

### Análise dos modelos de tráfego utilizando Erlang C - Aplicação no tráfego telefônico

**Erlang C -**  A fórmula de Erlang C é utilizada no estudo de sistemas com perdas e é utilizada para dimensionamento de recursos em qualquer sistema constituído por filas, inclusive em centrais de atendimento.

O modelo de tráfego Erlang C é baseado nas seguintes hipóteses:

- Um número infinito de fontes
- Padrão de chegada de tráfego aleatório
- Chamadas bloqueadas retardadas
- Tempos de espera distribuídos exponencialmente

O modelo Erlang C é projetado em relação à teoria de enfileiramento. Esse modelo presume um padrão de chamada de chegada aleatório; no qual o chamador faz uma chamada e é mantido na fila até que a chamada seja atendida. O modelo Erlang C é mais comumente utilizado em desenhos ACD (automatic call distributor) para determinar o número de agentes necessários (CHEUNG et al., 2002). Pode também ser utilizado para determinar a largura da banda de circuitos de transmissão de dados, mas não é o melhor modelo para essa finalidade.

No modelo Erlang C, é preciso saber o número de chamadas ou pacotes no horário de pico, a duração média das chamadas ou tamanho dos pacotes e o retardo esperado em segundos.