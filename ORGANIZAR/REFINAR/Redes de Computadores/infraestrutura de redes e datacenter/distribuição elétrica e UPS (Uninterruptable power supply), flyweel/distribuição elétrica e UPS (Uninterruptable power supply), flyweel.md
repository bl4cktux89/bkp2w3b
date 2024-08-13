A importância de se manter energizado o Data Center é tão grande que podemos considerar que o sistema de fornecimento ininterrupto de energia é o sistema mais crítico de um Data Center.

Criar uma estrutura de não interrupção de energia envolve dois componentes fundamentais. O primeiro é o UPS (_**Uninterruptable Power Suppy**_) e, tão importante como o primeiro, o gerador de Energia. Este segundo componente será tratado em um tópico específico.

Talvez o leitor possa estar pensando em o porquê de se separar estes componentes, mas, entendendo o funcionamento dos dois, ficará bem claro que tratam-se de equipamentos totalmente diferentes.

O UPS, também chamado de NoBreak, tem por objetivo, criar uma condição de introduzir uma fonte de energia sem que os equipamentos protegidos "sintam" que ocorreu uma falha no fornecimento de energia normal.

As aplicações de missão crítica como data centers, instituições financeiras, telecomunicações e governos tipicamente têm geradores e fontes de alimentação ininterrupta ( UPS ) para fornecer energia de backup para manter suas informações críticas  on-line. As topologias Tier I e Tier II, de acordo com ANSI / TIA- 942 são muito simples e diretas, sem redundância de vias, ou vias de distribuição única, mas, com componentes redundantes. Configurações de Tier III e Tier IV têm complexidade crescente com múltiplos caminhos de distribuição, manutenção simultânea e vários caminhos ativos. Este tópico irá explorar a compatibilidade, dimensionamento e considerações de design para UPSs em níveis Tier I, Tier II, III, e IV. A tabela 1 mostra esta relação.

![[Untitled 68.png|Untitled 68.png]]

Tabela 1. Relação da redundância de UPS para cada classificação e Tier

**Qual é a diferença entre N+1, 2 N e 2N+1?**

Uma maneira mais simples de olhar para N+1 é fazer uma paralelo com uma situação simples do dia-a-dia. Por exemplo, imagine que você fará uma reunião entre os gerentes de sua empresa e precisa dimensionar a sala de reuniões. Digamos que você tenha dez gerentes e precisa de dez cadeiras, mas apenas por precaução você prepara 11 cadeiras. "N" representa a quantidade exata de cadeiras que você precisa, e a cadeira adicional representa o +1. Portanto, você tem N+1 cadeiras para a reunião. Voltando aos datacenters, um sistema N+1, também chamado de redundância paralela, é uma segurança para garantir que um sistema de fonte de alimentação ininterrupta (UPS) está sempre disponível. N+1 representa o número de módulos UPS que são responsáveis pela demanda de energia para os sistemas conectados essenciais e, ainda, mais um, ou seja, 11 cadeiras para 10 gerentes representa menos chance de paradas.

Embora um sistema de N+1 contém equipamento redundante, não é, no entanto, um "sistema" totalmente redundante, pois ainda pode falhar porque o sistema é implementado em um circuito comum (único) que alimenta vários pontos em vez de duas fontes de alimentação completamente separadas.

Voltando ao exemplo da reunião. Se, diferentemente, você planeja uma reunião com um sistema de redundância 2N, então você teria as dez cadeiras os dez gerentes, além de um adicional de dez cadeiras, então 20 cadeiras. 2N é simplesmente duas vezes, ou o dobro da quantidade de cadeiras que você precisa. Em um Data Center, um sistema 2N contém o dobro da quantidade de equipamentos necessários, que funcionam separadamente, sem pontos únicos de falha. Estes sistemas 2N são muito mais confiáveis do que um sistema de N+1 porque eles oferecem um sistema redundante que pode ser facilmente mantido em regime regular, sem qualquer perda de potência. Em caso de uma falha de energia prolongada, um sistema 2N ainda vai manter as coisas funcionando. Alguns Data Centers (Tier IV) oferecem 2N+1, que é, na verdade, o dobro da quantidade necessária, mais uma parte extra de equipamentos, então de volta ao exemplo da reunião, 21 cadeiras.

2N+1 parece um exagero, mas, se considerarmos a criticidade dos serviços oferecidos, acaba não sendo mais dispendioso financeiramente do que a falha do serviço em si. O que precisamos perguntar, sempre, é: Qual o custo de perder o serviço? Se uma instituição financeira parar de atender sua necessidade (pagamento de uma conta de restaurante, por exemplo), você sairá para o concorrente. Você pode espalhar para os amigos. Quanto o fornecedor suportará em perdas?

**O que é um UPS?**

A figura 1 mostra um típico UPS (NoBreak) de um Data Center. Olhando assim parece um equipamento qualquer. Vamos entender melhor seu funcionamento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/2/270218/13179.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/2/270218/13179.jpg)

Figura 1: Imagem de um NoBreak

Já no esquema da figura 2, podemos observar algo importante logo na entrada do UPS/NoBreak. **A alimentação alternativa é a entrada CA do concessionário de energia elétrica**, ao contrário do que seria esperado. O bom uso do equipamento, sugere a alimentação contínua do Data Center pelo NoBreak. A alimentação de corrente alternada (CA) está sempre alimentando o NoBreak e o Data Center está sempre sendo alimentado pelo NoBreak. Isto é importante para garantir que o equipamento está funcionando, isto é, não se espera uma queda de energia para que o equipamento (Nobreak) entre em funcionamento e, somente assim, sabemos se está tudo ok. Por outro lado, não corremos o risco de pulsos de energia prejudiciais ocorram quando da falta energia.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/4/5/254580/13181.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/4/5/254580/13181.jpg)

Figura 2: Esquema básico de um NoBreak

Fonte: Autoria própria

Basicamente, o UPS recebe a corrente alternada (CA), transforma (Retifica) em corrente contínua, carrega as baterias e transforma (Inverte) a corrente contínua em alternada novamente para alimentar o Data Center. A CHAVE tem a função de passar direto da alimentação da concessionária para a saída, quando ocorre qualquer manutenção ou problema com o UPS/NoBreak.

A figura 3 mostra uma situação típica de organização das baterias de um NoBreak.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/2/270219/13185.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/2/270219/13185.jpg)

Figura 3: Organização de baterias de um UPS

O nome que se dá para a energia que sai do NoBreak e é entregue ao Data Center é ENERGIA CONDICIONADA. Isto porque é uma energia garantida, estável e sem harmônicas e picos.

Independentemente, apesar da recomendação acima, existem três tipos de UPS. Veja os esquemas básicos, simbólicos e genéricos na figura 4. Existem variações destes três tipos básicos, como o Double Conversion Online e o Delta Conversion Online, dois modelos característicos para grandes instalações. O entendimento destes três modelos básicos é o suficiente para o propósito deste material.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/4/6/254646/13185.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/4/6/254646/13185.jpg)

Figura 4: Figura 4: Esquemas dos tipos básicos NoBreak: Standby, Line Interactive e Standby Ferro

Fonte: Autoria própria

O modelo Standby é o mais simples e mantém a alimentação do Data Center pela energia vinda da concessionária. Ao ocorrer a falha da energia principal, entra em funcionamento a energia das baterias. É claro que, neste e nos outros modelos, existe um sensor de falta de energia principal que aciona automaticamente a chave seletora. Este modelo é relativamente falho, pois quando ocorre esta entrada acontecem picos e, ainda, a introdução de frequências espúrias no sistema de alimentação, podendo causar um mal funcionamento em algum equipamento mais sensível e menos protegido. Além disto também pode acontecer de que o sistema de baterias esteja com algum problema que será detectado apenas no caso de uso, provocando uma surpresa desagradável para todos.

O modelo Line Interactive é bastante usado para instalações médias. Segue mais a recomendação de melhores práticas para alimentação profissional de ambientes computacionais. A vantagem é que a alimentação do Data Center é sempre a mesma, não havendo picos e instabilidades na troca da alimentação. Também não ocorrem surpresas, pois alguma falha no sistema por baterias é facilmente percebida.  Também a manutenção é simples, pois a chave seletora serve como bypass do equipamento liberando-o para a manutenção.

O modelo Standby-Ferro é usado para características de instalações maiores e apresenta um comportamento parecido com o Standby, diferenciando-se pelo transformador de linha após a saída. Este transformador tem dois primários. Uma para a saída após o inversor e outro para a saída após alimentação CA. Como resultado, a troca de fonte de energia ocorre despercebida pelos circuitos alimentados devido ao isolamento causado pela separação metálica física entre as bobinas primárias com a bobina secundária. Além disto a característica indutora das bobinas é uma impedância para a passagem de picos.

NoBreaks/UPS são equipamentos complexos e a variação tecnológica não para de crescer. Um estudo mais profundo deste assunto é feito em cursos de engenharia elétrica. O importante é o leitor entender as diferenças básicas para poder dimensionar adequadamente um Data Center.

A entrega da energia do NoBreak ocorre através das vias instaladas de acordo com a norma. No caso de Tier IV, temos redundância de vias e cada estrutura de UPS é responsável por uma das vias.

Um cálculo rápido para dimensionamento de UPS é verificar a potência (kW) que ele vai ter que alimentar (um equipamento ou a soma das potências de vários equipamentos).

Descoberta a potência (kW), atribui-se um fator de potência (para cargas de informática de 0,8).

S(kVA) = P (kW)/FP.

O resultado será o valor mínimo do UPS. Prever futuros crescimentos.