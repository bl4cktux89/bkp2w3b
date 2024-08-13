**Introdução**

Cada um dos subsistemas possui uma série de detalhes que devem ser rigorosamente considerados no momento do projeto, portanto é fundamental que o projetista conheça em profundidade todos esses requisitos e possa aplicá-los em qualquer tamanho de projeto, seja ele de uma pequena rede com pouca quantidade de postos, seja ele uma rede com mais de 10.000 postos de trabalho.

O conhecimento das normativas e sua correta aplicação vão além do projetista, estende-se também ao quadro técnico responsável pela instalação e manutenção do parque de cabos.

Se essas premissas de boa engenharia forem seguidas e executadas, uma rede em tecnologia de cabeamento estruturado terá sua garantia de funcionamento assegurada por um período superior a 10 anos.

Ainda que nesse período surja alguma nova tecnologia não disponível nos dias atuais, os fabricantes dos produtos de cabeamento asseguram seu pleno funcionamento estendendo essa garantia por períodos superiores a 20 anos.

Antes do estudo dirigido de cada subsistema, vamos falar sobre as interferências eletromagnéticas (EMI) e as complicações que elas exercem nos sistemas de cabeamento estruturado.

**Interferências eletromagnéticas**

As interferências eletromagnéticas são um dos problemas mais graves que poderá ocorrer em um sistema de cabeamento metálico.

Isso se deve ao fato de que as interferências eletromagnéticas são ondas irradiadas que podem muito bem aparecer no cabeamento como um ruído, prejudicando a comunicação binária pela deformação do pulso digital. Em uma instalação de rede em tecnologia de cabeamento estruturado deve-se evitar que os cabos passem perto de fontes de interferência, como:

- Motores elétricos;
- Reatores de lâmpadas fluorescentes;
- Máquinas fotocopiadoras;
- Máquinas elétricas com circuitos ceifadores com SCR ou Tiristores;
- Cabos de energia (Ramais alimentadores);
- Circuitos controladores de iluminação (dimer).

Sempre devem ser observadas as normas locais de segurança quanto à instalação de sistemas elétricos e de comunicação de dados.

A norma EIA/TIA569, de 1991, utilizava uma tabela para distanciar esses dois sistemas (tabela a seguir), baseada na interferência que poderia ocorrer, porém sem um estudo mais apropriado de laboratório com as interferências e as novas redes que estavam surgindo.

Separação de cabos elétricos e de dados (Antiga Norma EIA/TIA569 – 1990)

![[Untitled 52.png|Untitled 52.png]]

Após a reedição da norma EIA/TIA569, que em 1997 recebeu a letra A, ficando então conhecida como ANSI/TIA/EIA569-A, estabeleceu entre outras coisas que não haveria mais a necessidade de uma distância entre cabos de telecomunicações e cabos de energia, cujas correntes não ultrapassassem o limite de 20 A (Amperes) em circuitos de 127 a 240 V (volts), exigindo apenas uma separação mecânica entre os cabos dos circuitos para fins de segurança física (curto circuito, sobrecargas, choques etc.).

**Work area – WA (Área de trabalho)**

A área de trabalho é o espaço dedicado para que os funcionários realizem suas atividades diárias. Em teoria geral, têm-se 10 m² como uma dimensão capaz de acomodar uma pessoa com o computador, telefone, mesa e cadeira dentro de um escritório comercial.

Nela, encontra-se o ponto de telecomunicações, que deverá possuir no mínimo duas tomadas de telecomunicações, sendo que o recomendado são três tomadas.

As tomadas normalizadas são conectores do tipo M8V (RJ 45) de 08 vias (04 pares) ou acopladores ópticos multímodo, conforme a solicitação do projeto e do cliente.

Segundo a normativa ANSI/TIA-568-C1 as seguintes combinações de cabos e tomadas podem ser utilizadas na área de trabalho (WA).

- Como 1º ponto: cabo de par trançado Categoria 5e ou superior de quatro pares, 100 , UTP (sem blindagem) ou F/UTP (com blindagem);
- Como pontos adicionais: cabo de par trançado Categoria 5e ou superior de quatro pares, 100 , UTP (sem blindagem) ou F/UTP (com blindagem) ou;
- Cabo óptico multímodo de 50/125 µm, fibras otimizadas para laser OM3 ou;
- Cabo óptico multímodo de 62,5/125 µm.

Na prática, para a maioria das instalações, recomenda-se que ambas as tomadas de telecomunicações sejam terminadas com cabos UTP/F/UTP, de quatro pares, 100

, Categoria 5e ou superior.

Para projetar a quantidade de áreas de trabalho que um cliente precisará, é necessário o fornecimento de um layout prévio produzido por um arquiteto. O layout é uma planta detalhada em escala demonstrando o local exato de todos os móveis e usuários que irão compartilhar aquele espaço, portanto basta o projetista solicitar o layout e começar seu trabalho a partir daí.

Modelos de Tomadas de Telecomunicação – RJ 45.

Para projetar a quantidade de áreas de trabalho que um cliente precisará, é necessário o fornecimento de um layout prévio produzido por um arquiteto. O layout é uma planta detalhada em escala demonstrando o local exato de todos os móveis e usuários que irão compartilhar aquele espaço, portanto basta o projetista solicitar o layout e começar seu trabalho a partir daí.

Quando o cliente não dispuser de um layout e nem ter ideia da quantidade de usuários que ocuparão o recinto, então se aplica a regra da normativa, que diz que uma WA deverá ter 10 m² dividindo o espaço disponível pela quantidade de WA.

As tomadas de telecomunicações podem ser instaladas em espelhos padrão 4 x 4" ou 4 x 2" ou ainda em caixas de superfície conhecidas como _**surface Box.**_ Também podem ser instaladas diretamente em espaços de painéis do próprio mobiliário de escritórios. Lembre-se de que nessa última opção a regra quanto à separação física dos cabos de telecomunicação e cabos elétricos continua valendo.

Modelo de espelhos com tomadas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104460/a06i03_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104460/a06i03_cabestru80_100.jpg)

Outra observação importante é que as tomadas de telecomunicações devem sempre ser instaladas ou estar próximas às tomadas elétricas para a alimentação dos equipamentos ativos da área de trabalho (WA).

As tomadas de telecomunicações em uma área de trabalho devem ser instaladas de forma a evitar poeira, água, metais (clips e grampos), agentes químicos de limpeza ou qualquer outro material que possa se alojar em seus contatos causando danos. Portanto, é altamente recomendada a utilização de tomadas que possuam portas removíveis ou basculantes para a sua proteção no caso de não estarem sendo utilizadas.

Todas as tomadas de telecomunicações devem ser terminadas com cabos UTP ou F/UTP utilizando uma das seguintes configurações reconhecidas por normas, a T568A ou a T568B, em que temos as seguintes cores correspondendo a cada pino em uma sequência ordenada:

![[Untitled 1 36.png|Untitled 1 36.png]]

Para ilustrar o que foi explicado, a figura a seguir demonstra em detalhes:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104462/a06i05_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104462/a06i05_cabestru80_100.jpg)

Os cabos que interligam os equipamentos (telefones, computadores, vídeos, fax etc.) às tomadas de telecomunicações devem ter as mesmas características dos utilizados no cabeamento horizontal.

Por exemplo, se houver uma instalação de Categoria 6 e os cordões de equipamento com Categoria 5e, o desempenho dessa rede ficará limitado ao da menor categoria.

Normalmente esses cabos devem ser flexíveis, em virtude das movimentações que habitualmente ocorrem no ambiente de escritório (limpeza e mudança de posição),dessa maneira, os patch cords de conectores modulares (RJ-RJ) **não podem ser fabricados em obra**, segundo a normativa EIA/TIA568-B e a resolução 242, de 30 de novembro de 2007, da ANATEL, tornando obrigatória a confecção em fábrica e testes um a um para NEXT e Return Loss com equipamentos adequados e com emissão de laudo comprobatório afixado na embalagem do cabo de manobra "patch Cord".

Fazem parte da área de trabalho as adaptações especiais necessárias à interligação dos equipamentos de telecomunicações com os serviços disponíveis. Entre elas, destacam-se:

- Cordões com conectores diferentes nas duas pontas;

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104464/a06i06_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104464/a06i06_cabestru80_100.jpg)

- Adaptadores em "Y": utilizados para compartilhar serviços semelhantes por meio de um mesmo cabo.

Esse adaptador serve para resolver situações emergenciais até que um novo cabo seja lançado e não deve ser considerado no projeto inicial.

- Adaptadores passivos: utilizados quando for preciso interligar cabos e tomadas com impedância ou pinagem diferente (por exemplo, baluns);
- Adaptadores ativos: utilizados quando o equipamento do usuário e o de telecomunicações utiliza técnicas de sinalização diferentes.

**SAIBA MAIS**

**WA**: Uma WA deverá ter no mínimo 2 tomadas de telecomunicações, sendo o recomendado 3 tomadas. Para a distribuição das WAs, basta seguir um layout apresentado pelo seu cliente, porém, na falta de um, a regra é a instalação de 1 WA para cada 10 m². As duas tomadas de telecomunicações devem ser terminadas sempre com a utilização da configuração T568A ou T568B e todas as tomadas e patch panels do cabeamento deverão seguir apenas uma configuração.

**Patch cords**: Os patch cords também devem ser da mesma categoria instalada nos cabos UTPs ou F/UTPs da obra. Os patch cords devem ser flexíveis e jamais serem montados na obra, devendo ser confeccionado em fábrica e testados adequadamente.