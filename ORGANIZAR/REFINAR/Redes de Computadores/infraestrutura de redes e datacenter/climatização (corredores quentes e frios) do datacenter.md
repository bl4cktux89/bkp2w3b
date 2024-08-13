A energia consumida para o carregamento de baterias, motores, transistores, chips, etc., além de produzir o trabalho para a qual foi designada, tem parte de seu efeito na produção indesejada de calor.

O sistema localizado no Data Center responsável pelo controle do ar, principalmente do calor é o HVAC System (Heat, ventilation, and air conditioning). É fundamental que todo o data center esteja sob o controle e domínio do HVAC. Aqui trabalharemos mais especificamente com a aplicação do HVAC com respeito ao Computer Room.

Se um computer room não tem um HVAC específico, deve, ao menos, estar próximo a um e com acesso priorizado. O HVAC deve ser projetado para trabalhar 24 horas por dia, 365 dias por ano.  Independente da classificação do Data Center, um backup do HVAC deve ser provisionado. Não há como dimensionar o efeito de uma falta de refrigeração, o custo de uma redundância é insignificante em comparação com os efeitos de uma falha sem reposição.

Os parâmetros que devem ser assegurados para um Data Center são:

- Temperatura de Bulbo Seco: 20 °C (68 ºF) a 25 °C (77 ºF);
- Umidade Relativa: 40% a 55%;
- Máximo ponto de orvalho: 21 °C (69.8 °F);
- Máxima faixa de variação: 5 °C (9 °F) por hora;
- Equipamento de umidificação e desumidificação pode ser necessário dependendo das condições ambientais.

**Distribuição de Equipamentos:**

Basicamente, a melhor maneira de manter a temperatura em um Data Center, consiste em, primeiro organizar a distribuição dos racks de forma que a frente dos servidores fique virada para o mesmo corredor, ou seja, os racks ficam “de frente” uma para o outro. Portanto, a parte traseira do rack fica apontando para a parte traseira de outro rack. Sempre as frentes dos racks estão apontadas para o mesmo corredor (considerando duas fileiras de racks). Na figura 1 podemos observar bem esta configuração. O corredor da frente dos racks (frente dos servidores) é chamado de corredor frio (Cold Aisle) e o corredor onde as traseiras dos racks se encontram é chamado corredor quente (Hot Aisle). A parte de cima do corredor frio, frequentemente, mas não sempre, é fechada ou o teto é mais rebaixado criando uma pressão que impede parcialmente que o ar saia por cima. A parte de cima do corredor quente é aberta ou contém grades com pressão negativa, ou seja, existe um vácuo acima das grades “puxando” o ar deste quente corredor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/2/272266/14227.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/2/272266/14227.jpg)

Figura 1: Corredor quente e frio

Fonte: shutterstock 256221169

**Como funciona o resfriamento?**

O ar frio entra no corredor frio (em frente aos servidores) por baixo, muitas vezes este ar frio é insuflado sob o piso (piso elevado) e, este piso, possui grades por onde o ar frio pode subir. O ar frio é impedido de simplesmente subir, em vez disto este ar é forçado pelas aberturas do rack para atravessar os servidores e equipamentos saindo por trás do rack. Nesta passagem o ar frio “roubou” o calor dos equipamentos e já sai quente na traseira do rack. Como é quente, sobe naturalmente para as entradas/grades que existem no teto. Este ar quente é sugado para fora do Data Center, ou, algumas vezes, é reutilizado para outros objetivos, como é o caso de um dos maiores Data Centers da Europa o Telecity em Paris, mostrado na figura 2. Este Data Center utiliza o calor para manter uma estufa onde cultivam-se plantas. Algumas vezes o mesmo ar quente passa por um sistema que o recupera e resfria, mas isto não é melhor caso de economia que podemos comentar.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/1/273159/data-center-estuda.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/1/273159/data-center-estuda.png)

Figura 2: Data Center Telecity e estufa de plantas que aproveita o ar quente.

Fonte: http://www.telecitygroup.com/

Desta forma, a _**computer room**_ mantém os equipamentos (servidores, roteadores, etc) frios. A subida do ar quente ajuda a criar uma sucção que puxa mais ainda o ar frio para forçá-lo pelos equipamentos.

**Mas, como funciona o equipamento que cria, ou produz, o ar frio?**

O ar frio é criado pelo CRAC (C_**omputer Room Air Conditioned**_). Existem várias técnicas para o resfriamento do ar. Estas técnicas utilizam propriedades e leis da física específicas para cada técnica. Algo que deve ser considerado, em primeiro lugar, é a temperatura e umidade do ar que está entrando no CRAC para ser resfriado. Claro que resfriar um ar mais seco com temperatura baixa é mais fácil que seu oposto, um ar mais úmido e com temperatura alta. A explicação sobre a temperatura é mais simples: Se precisamos chegar a uma temperatura de 20°C e o ar já está à 25°C, é claro que o esforço do equipamento em tempo e energia para baixar  5°C será menor, enquanto que, se o ar entrante estiver à 35°C, precisaremos de maior tempo e energia para baixar 15°C. Já a explicação da questão da umidade (quanto maior, mais difícil resfriar o ar), é bem mais complexa, mas podemos resumir assim: a água consegue manter muito mais calorias do que o ar, então, com água presente no ar precisamos resfriar o ar e a água. Muito mais difícil.

Vários equipamentos podem ser usados para o condicionamento do ar que irá entrar no CRAC, mas, algumas vezes, o ar que sai dos corredores quentes já está numa temperatura abaixo do que o ar natural da região onde o Data Center está sediado. Neste caso, o ar é puxado dos corredores quentes, pode ou não passar por resfriadores que na verdade são radiadores resfriados por ar forçado ou por água, como no caso dos radiadores dos motores dos automóveis. Quando é utilizado água, e isto ocorre sempre em grandes Data Centers, um equipamento chamado Chiller (são unidades chamadas _**Chilled Water Units**_ ou, mais comum em Data Centers, CRAHs - _**Computer Room Air Handlers**_) é responsável por manter a água de resfriamento fria. São equipamentos gigantescos que são externos ao Data Center. Veja a figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/7/270739/14242.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/7/270739/14242.jpg)

Figura 3: Chiller externo ao Computer Room

O ar que entra no ar condicionado (CRAC) é empurrado por uma ventoinha contra um conjunto de serpentinas frias chamado evaporador (veja a figura 4 uma unidade interna com evaporador) e sai do outro lado já resfriado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/1/273162/unidade-crac.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/1/273162/unidade-crac.png)

Figura 4: Unidade CRAC. Cortesia da TCSolutions - Total Care for Your Business

Fonte: http://www.tcsolutions.com.br/pt_br/

Neste processo, a umidade em forma de vapor, que estava neste ar, condensa como numa garrafa gelada de refrigerante, e goteja caindo em um sistema de captação que a leva para fora. Mas, como estas serpentinas estão frias?  Bem, dentro delas existe um líquido gelado. Este líquido é especial chamado “liquido refrigerante”. Ele tem umas propriedades físicas que criam o seguinte comportamento: Começando pelo lado frio, este líquido está à 7°C (depende da substância). Quando o ar passa quente na serpentina fria, ele se resfria porque deixou o calor na serpentina. O líquido refrigerante vai saindo da serpentina em estado de gás. Este gás é comprimido pelo compressor (responsável pelo barulho típico de um ar condicionado, mas geralmente esta parte é externa). Neste momento sua temperatura até aumenta e fica sob alta pressão. Ao passar pelo condensador (geralmente uma serpentina) onde outra ventoinha resfria as aletas desta serpentina e o gás torna-se líquido novamente. Estes condensadores são muito grandes e são externos, como os chilliers. Veja como são os condensadores na figura 5.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267911/14252.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267911/14252.jpg)

Figura 5: Condensadores na cobertura de um prédio.

Fonte: shutterstock 99962894

A passagem pelo condensador já deixa o líquido mais frio, mas o que esfria mesmo é uma reação ocorrida em um orifício. O líquido, que ainda está sendo empurrado pela força residual do compressor, passa em um pequeno orifício e, ao expandir-se na saída, resfria-se fortemente. Está é uma reação físico-química cujo resultado é a perda de temperatura pela expansão. A figura 6 demonstra este funcionamento. Este é o funcionamento básico que utiliza o sistema de expansão para o resfriamento.

Existem outras técnicas que envolvem glycol, áqua gelada ou resfriada e, ainda outros, mas não é escopo deste material.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/2/268257/14256.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/2/268257/14256.jpg)

Figura 6: Funcionamento de um condicionador de ar comum.

Fonte: . Fonte: www.adias.com.br/funcionamento_do_ar

Este ciclo de refrigeração se mantém e garante o resfriamento do data center. Dependendo do tamanho do data center, podem existir vários CRACs  para melhor garantir o resfriamento.