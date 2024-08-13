  

### Introdução

A coleta de dados para Menascé e Almeida (2002) é fundamental para uma gestão eficaz quando pensamos em TIC, consiste no ato de pesquisar, coletar dados da rede, coletar dados de servidores, juntar documentos e provas, de forma a facilitar uma posterior análise.

A internet é um organismo vivo em constante expansão. Os principais fatores para crescimento dos serviços web são as migrações de serviços tradicionais para a internet, a criação de novos serviços virtuais, os benefícios de escala e custo e a acessibilidade (KUROSE, 2006). Mostraremos alguns estudos de casos com dados coletados e formatados que ajudarão a avaliar os acordes de nível de serviço entre o cliente e a empresa, evidenciando que um planejamento malfeito poderá trazer enormes prejuízos à empresa.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/2/4/322484/19887.gif)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/2/4/322484/19887.gif)

Coleta de Dados

### Metodologia para coleta de dados

Comenta Claise e Wolter (2011) ao iniciar um trabalho de análise de desempenho, algumas perguntas devem ser respondidas, pensando em cada tipo de serviço ou aplicação na rede:

1. O que coletar?
2. Quem é o usuário?
3. Como medir?
4. Onde coletar?

### 1 - Detalhes da coleta de dados: o que coletar ?

Pensando em redes de computadores a resposta depende do problema, as informações mais importantes e mais usuais segundo Claise e Wolter (2011) são apresentadas abaixo.

- IP source address
- IP destination address
- Source port
- Destination port
- Protocol field
- ToS field
- Input or output (sub)interface

Destes elementos podemos extrair diversas informações, como:

- Utilização de CPU no elemento de rede à medida que mais registros de dados são classificados e processados;
- Utilização de memória no elemento de rede à medida que mais registros de dados são mantidos;
- Largura de banda entre o elemento de rede e o gerenciamento para transferir os dados;
- Dados processados e mantidos pelo sistema de gerenciamento de rede.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/8/347836/27333.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/8/347836/27333.jpg)

Usuários de redes

### 2 - Detalhes do usuário

Muitos aplicativos exigem a conta do usuário: monitoramento e criação de perfis de usuários, faturamento, análise de segurança e assim por diante (CLAISE; WOLTER, 2011). Sendo assim alguns itens devem ser levados em consideração.

- Qual é a precisão da base de dados da conta dos clientes?
- No caso de alterações na atribuição de características de rede (endereço IP, endereço MAC, VPN, PVC ou equivalente), qual é o processo para atualizar o banco de dados?
- Em caso de alterações na alocação de características de rede, quanto tempo demora a atualização antes de o banco de dados estar atualizado?
- Os usuários múltiplos em um local (como uma rede doméstica) usam as mesmas características de rede?

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/1/1/291128/17218.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/1/1/291128/17218.png)

Segmentos de rede

### 3 - Métodos de medição: como coletar registros de dados

Para Claise e Wolter (2011) com uma definição clara do que coletar e quem é o usuário, a questão de como coletar registros de dados torna-se relevante. Os seguintes detalhes precisam ser considerados para medição:

- Posição de onde coletar os dados, na interface do dispositivo ou no core da rede;
- Coleta unidirecional ou bidirecional;
- Precisão da coleta;
- Granularidade, que significa agregar pacotes em fluxos ou agregar múltiplos medidores em um único valor;
- Algoritmo de coleta, significa inspecionar cada pacote com uma coleção completa, ou apenas alguns pacotes por amostragem;
- Inspecionar o conteúdo do pacote para seleção com filtragem;
- Adicionar detalhes aos conjuntos de dados coletados, tais como etiquetas de data, hora e somas de verificação;
- Detalhes de exportação, como protocolos, frequência, compressão e segurança.

### 4 - Posições de medição: onde coletar registros de dados

Depois de decidir como medir, o próximo passo será onde posicionar os dispositivos de medição da rede. Considere as seguintes opções para posições dos medidores:

- Ponto de medição na borda oposta ao núcleo da rede.
- Ponto de medição no elemento de rede ou no dispositivo do usuário final.
- Alavancar agentes integrados em elementos de rede ou implantar sondas dedicadas.
- Pacotes de ingresso em comparação com os pacotes de egresso.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293463/18772.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293463/18772.png)

Pontos de coletas de dados

### Desempenho de um website – Caso 1

Uma rede virtual de revenda de equipamentos oferece, aos usuários de um website, visitas para consultar e enviar requisições de compra de produtos eletrônicos, distribuídos em várias revendas espalhadas pelo território nacional.

A base de dados possui uma gama completa de produtos, que consiste em imagem, marca, valor e outras informações, como características técnicas e funcionais, e é totalmente acessível na web. Possui, ainda, alguns tipos de requisições, como:

- Pedidos de documentos e imagens.
- Requisições de consulta no banco de dados de acordo com os critérios: marca, modelo e distância do frete.
- Pedidos de compra.

É importante que o tempo de resposta do website seja aceitável, em caso contrário, os usuários utilizarão outros sites e a empresa acabará perdendo negócios e, assim, haverá prejuízos.

A revenda virtual de produtos deseja negociar novos acordos de parceria com outras empresas, o que aumentará a disponibilidade dos produtos e o número de requisições enviadas ao site. Os novos acordos serão inseridos gradualmente e deverão aumentar a taxa atual de chegada de pedidos em 10% no primeiro estágio, depois 20% e, finalmente, 30%.

A aplicação mais crítica é a transação de consulta. Foi observado que se o tempo de resposta para essa transação ultrapassar os 4 segundos, mas permanecer abaixo dos 6 segundos, 65% das transações de consulta serão perdidas, pois os usuários cancelarão a consulta e vendas em potencial não serão realizadas. Se o tempo de resposta for superior a 6 segundos no servidor web, então 95% dos pedidos de consulta serão cancelados. A esses limites superiores no tempo de resposta chamamos de Níveis de serviço. Outros exemplos são:

- Taxa de processamento (Throughput) taxa de processamento mínima exibida por um servidor (por exemplo, pelo menos 100 pedidos web processados por segundo).
- Disponibilidade mínima do website (por exemplo, o website deve estar disponível por, pelo menos, 99,99% do tempo).
- Porcentagem de transações que emitem um tempo de resposta inferior ou igual a certo valor (por exemplo, 95% das transações deverão exibir um tempo de resposta que não ultrapasse os 2 segundos).

### Disponibilidade de servidores WEB - Caso 2

Vamos aplicar alguns conceitos, utilizando dados de logs de registros dos servidores, para melhorar a disponibilidade. Podemos aplicar dois itens, o primeiro é a redução da frequência de falhas (+ MTTF) e a segunda é a redução do tempo de recuperação (- MTTR), neste caso devem ser observados os seguintes itens:

- Tempo para detectar a falha.
- Tempo para diagnosticar a causa da falha.
- Tempo para determinar possíveis soluções.
- Tempo para corrigir o problema.
- Log — Histórico de recuperações passadas auxiliam na diminuição do MTTR.

Considere um website composto de dois servidores web: um de aplicação e um de banco de dados. Supondo que os dados históricos mostrem que o servidor de aplicação é reinicializado a cada 20 dias em média, ficando por um período de 10 minutos indisponível, calcule qual a disponibilidade do servidor de aplicação.

A primeira etapa é descobrir o MTTF, assim temos:

**MTTF = 20x24x60 = 28.800**           

Ou seja, os 20 dias de parada vezes 24 horas por dia vezes 60 para achar o valor em minutos.

Agora calcularemos a disponibilidade.

**Disponibilidade = MTTF / (MTTF + MTTR)**

**Disponibilidade = 28.800 / (28.800 + 10) = 0,99965, ou seja: Disponibilidade = 99,9% um sistema bem controlado**

Vamos analisar agora a razão entre confiabilidade e disponibilidade de um sistema. Sabemos que:

- Confiabilidade: é a probabilidade de que o sistema esteja funcionando correta e constantemente por um período de tempo determinado.
- Disponibilidade: baseia-se na noção de que um componente (ou sistema) alterna por períodos em que está operacional (ou períodos ativos) e períodos em que está parado (ou período inativo).

Analisemos agora a confiabilidade de um sistema.

Um sistema baseado em componentes apresentará a confiabilidade produto de seus itens.

Imaginemos um website composto por:

- Servidor web com disponibilidade de 0,9.
- Servidor de aplicação com disponibilidade de 0,95.
- Servidor de banco de dados com disponibilidade de 0,99.

**Confiabilidade = 0,9 x 0,95 x 0,99 = 0,84645.**

Com base neste cenário, determine o aumento da disponibilidade no site melhorando 0,05 no componente de maior impacto na disponibilidade geral.

**Servidor web passa para 0,95, sendo assim: Confiabilidade = 0,95 x 0,95 x 0,99 = 0,89348**

### Transferências de Arquivos - Caso 3

Sabemos que links de conexão normalmente se medem em Kbps ou Mbps (kilobits e megabits) por segundo e que para achar as taxas a partir de conversão de bytes, deve-se sempre multiplicar por oito (byte em bit).

Sendo assim, analisemos o cenário de uma empresa que necessita transferir 70 figuras de 8KBytes cada uma, através de um link de dados de 256kbps. O gerente de TI quer saber quanto tempo demora essa transmissão.

Calculemos:

Tempo = (70 (figuras) X 8 (Kilobytes) X 8 (convertendo para bits)) / 256 (Banda)

Tempo = (70 X 8 X 8) / 256

Tempo = 17,5 segundos

### Upgrade do ambiente – Caso 4

A empresa ABC Tecnology possui 60.000 funcionários, interligados pela intranet, que permite aplicações para treinamento, Rh, despesas de viagem, Help-Desk (atendimento de dúvidas) e notícias. A sua aplicação de Help-Desk é a principal do sistema onde 10% dos funcionários enviam uma requisição ao Help-Desk, em média, todos os dias, 70% das requisições entre 10h00 e 12h00 e 14h00 e 16h00. A empresa deseja mudar o SO dos desktops e isso deve dobrar o tempo de resposta.

Vamos calcular primeiro a quantidade de requisições que são feitas no sistema.

Requisições = (60.000 x 10% x 70%) = 4.200 requisições durante 4 horas de pico.

Requisições = 4.200

Baseado no período de pico que de acordo com o cenário é de 4 horas, qual número de requisições/segundo atual no pico?

Total de Requisições no pico = (4.200 / 4 / 3.600)

Total de Requisições no pico = 0,29 requisições/segundo

Calculamos então o total de requisições, dividido pelo período de 4 horas e dividimos por 3.600 para acharmos o valor por segundo. Neste caso, podemos ainda sugerir para esse cenário num eventual upgrade do ambiente a troca de CPU, a inclusão de mais processadores, a inclusão de mais discos no servidor, a divisão de carga de trabalho, entre outras melhorias.