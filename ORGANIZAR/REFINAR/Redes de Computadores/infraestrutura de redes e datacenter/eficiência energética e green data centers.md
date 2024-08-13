Data Centers são ambientes de missão crítica e requerem integração entre todas as utilidades. É composto por várias áreas trabalhando em um mesmo ambiente de forma integrada. Dentre essas áreas, pode-se citar telecomunicações, responsável pelo cabeamento estruturado, engenharia elétrica, responsável por fornecimento de energia, grupos geradores, nobreaks, etc, engenharia mecânica, responsável pela área de refrigeração, área de segurança eletrônica, e outras áreas.

Um Green Data Center é aquele que pode operar com a máxima eficiência energética e impacto ambiental mínimo.  Isso em todas as áreas citadas acima. O consumo de energia elétrica em um data center é a grande preocupação. Quanto maior a disponibilidade oferecida pelo data center, maior é o consumo de energia dos equipamentos de TI e de refrigeração.

Para se ter uma ideia, 1 MW  consumidos em um data center de alta disponibilidade pode consumir U$ 20.000.000,00 de eletricidade durante sua vida útil. Artigos recentes sugerem que, para alguns clientes, o custo da eletricidade é maior do que o custo do hardware de TI.

Um Green Data Center deveria ser pensado desde o projeto inicial, na construção civil, na sua localização, com otimização e economia dos recursos naturais.

**Eficiência Energética**

Existem vários métodos de se medir a eficiência de um data center. Um deles foi criado pela _**The Green Grid**_, formado por um consórcio de empresas de TI, para tratar dos aspectos de consumo de energia elétrica, bem como requisitos de climatização em um data center.

_**The Green Grid**_ criou a métrica PUE (_**Power Usage Effectiveness =**_ eficiência no uso de energia elétrica).

Num data center ideal, toda a energia fornecida seria consumida pelos equipamentos de TI. Mas, num data center real, isso não acontece. Existem outros consumidores de energia além dos equipamentos de TI, como por exemplo, transformadores, UPS, aparelhos de ar condicionado, umidificadores, iluminação, etc. Alguns desses dispositivos, como UPS e transformadores estão no caminho da energia para as cargas de TI.

A energia que conta em data center é a energia que realmente alimenta as cargas de TI. O PUE mostra quanto da energia recebida vai para as cargas de TI e quanto vai para os outros consumidores do data center. A figura 1 mostra bem o caminho da energia em um data center.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/1/5/271569/15041.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/1/5/271569/15041.jpg)

Figura 1: Fluxo da energia em um data center

Fonte: http://it-resource.schneider-electric.com/i/482260-wp-154-electrical-efficiency-measurement-for-data-centers

PUE é determinado dividindo a quantidade de energia entrando em um data center, pela energia utilizada pelos equipamentos de TI:

PUE = Potência Total do Data Center

Potência Total de TI

Apesar da fórmula simples, não é fácil definir o que é carga de TI, o que é carga da infraestrutura e o que pode ser excluído.

Outra medida é o DCiE (_**Data Center infraestructure Efficiency =**_ Eficiência da infraestrutura de um data center). É uma métrica inversa da PUE e mostra a eficiência energética em percentuais:

DCiE = Potência Total de TI    x 100 = 1/PUE

Potência Total DC

Por exemplo, vamos supor que o data center inteiro consuma 1500 kW.  Desses 1500kW, 1000kW abastecem às cargas de TI, portanto:

PUE = 1500/1000 = 1,5

DCiE = 1/1,5 = 0,6667 x 100 = 66,67%

Portanto, quanto mais perto de 1 ou 100%, melhor a eficiência do data center. Mas, para que chegue nesse valor, toda energia consumida deveria ser entregue aos equipamentos de TI e isso é impossível, pois é necessária a refrigeração, UPS, iluminação e demais sistemas que mantém o funcionamento de um data center.

Um data center PUE 2 informa que as cargas de TI consomem a metade da energia fornecida e a outra metade vai para as outras cargas.

Percebe-se que o interessem em diminuir o consumo de energia não é só ambiental, mas também financeiro. Os custos com eletricidade são enormes, associados com o custo de operações. Isso significa que, diminuindo os custos com eletricidade, ganha-se em competitividade.

Se acordo com pesquisas, os dois maiores consumidores de energia elétrica em data center são:

- Infraestrutura de suporte (climatização, etc.): 50% do total.
- Servidores gerais: 34% do total

Com esses dados, vários avanços ocorreram nessas áreas.

Servidores _**blade**_ de alta densidade estão oferecendo uma maior capacidade de processamento por watt de energia.

A virtualização de servidores está permitindo reduzir o número de servidores, em uma estrutura onde o número de servidores foram super dimensionados.

Equipamentos com o selo _**Energy Star**_ (indica que o produto consome menos energia que outros produtos da mesma categoria) contribuíram para reduzir o consumo de eletricidade com equipamentos de TI e de Infraestrutura.

A adoção de uma nova tecnologia de interconexão de redes utilizando o paradigma STIA (_**Space-Time Interconnection Architecture =**_ Arquitetura de Interconexão baseado no espaço-tempo), mostrou-se muito mais eficiente para suportar a alta densidade de tráfego entre servidores_**, storages**_ e equipamentos de telecom. Trata-se de equipamentos de comutação de rede, conectados por fibra que também operam baseados na luz.

A automação e monitoramento de ambientes de missão crítica também trazem benefícios na eficiência da gestão global dos data centers.

Portanto, a medição da eficiência do data center é para administrar o uso de eletricidade. Tomar medidas para controlar o uso elétrico requer o conhecimento de:

- As fontes de ineficiência
- Oportunidades de melhoria
- Os benefícios esperados da melhoria da eficiência

Fazendo uma simples medição da eficiência do data center é interessante, mas não é só isso. Deve-se levar em consideração modelos comparativos pelos quais pode-se entender as implicações das medidas feitas e planejar melhoramentos.