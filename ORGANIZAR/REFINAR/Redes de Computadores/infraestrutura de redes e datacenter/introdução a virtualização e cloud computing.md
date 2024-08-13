Virtualização é a chave atual para qualquer tentativa de se ter disponibilidade e garantia de um Data Center no modelo _**Green Data Center**_ (uma forma de comparar o verde da natureza com um Data Center que não a agride). Esta capacidade de agredir menos a natureza significa, basicamente, gastar menos energia. O que a virtualização faz, simplificadamente, é utilizar um servidor físico fazendo o papel de mais que um servidor. Isto é feito aproveitando a ociosidade da capacidade real do servidor instalando outros servidores, através de algo que chamamos de máquinas virtuais. O sistema operacional original do computador físico é tapeado por um software especializado chamado de _**HYPERVISOR**_ que finge estar sendo uma aplicação comum usando os recursos físicos do computador, enquanto, do outro lado, na visão dos sistemas instalados na máquina virtual, existe uma máquina real os suportando. O  _**hypervisor**_   está sempre fingindo dos dois lados. Um modelo simbólico pode ser visto na figura 1. Existem dois tipos; o _**bare-metal**_ que controla o hardware, ou seja, é o próprio sistema operacional, e o _**client/hosted**_ ou _**type**_ 2, que fica no instalado no sistema operacional da máquina física. Veja a figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/6/272601/15108.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/6/272601/15108.jpg)

Figura 1. Uma idéia figurativa sobre virtualização.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/0/270047/15109.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/0/270047/15109.jpg)

Figura 2. Tipos de Hypervisor

Fonte: (http://www.ibm.com/developerworks/cloud/library/cl-hypervisorcompare/)

Quando as máquinas virtuais foram criadas, as coisas não faziam muito sentido. Por que os servidores eram ociosos? Eles foram comprados por profissionais de TI que haviam superestimado o serviço a ser feito e obrigaram os investidores da empresa a comprarem algo caro, mas sem uma função específica? Como qualquer novidade em TI as máquinas virtuais começaram a ser usadas. Este problema de existirem servidores ociosos ficou meio que escondido. Também existia uma ideia de que o servidor supra capacitado o era porque em certo momento a aplicação hospedada nele precisava usar toda a capacidade. Bem, então a outra máquina virtual instalada deveria dar licença para a aplicação principal nestes momentos? Alegava-se que comprar servidores menores consumiriam na soma, mais energia. Mas, então existem perdas de engenharia na produção dos computadores? Estas perguntas nunca foram respondidas. O avanço da tecnologia, algumas vezes, passa por um uso apenas por modismo e, mais tarde, dominada a tecnologia, aparece um uso mais importante para a novidade, e foi o que aconteceu.

Paralelamente, o mercado também estava com um produto para vender que não alcançava as expectativas. Era a vez do SaaS (_**Software as a Service**_), ou seja, o usuário não tem o software, mas fazia o uso dele. É claro que isto acontece remotamente e pela internet. Muitos eram os motivos para ninguém embarcar nesta novidade, pois a ideia de ter seus dados em outro lugar controlado por outra pessoa, a possibilidade de não ter certeza que suas customizações seriam feitas e a ideia que se você precisasse crescer, ficaria na mão do aluguel a qualquer preço, impediam que este produto de decolar no mercado.

Neste momento surgiu a ideia do _**Cloud Computing**_ (Computação em nuvem). Caiu como luva para tirar a virtualização do simples modismo para a “coisa” mais certa a se fazer e, também, viabilizou também o custo e maleabilidade do SaaS, crescendo este mercado para mais dois serviços importantes o IaaS (Infraestrutura como um serviço). Isto é uma verdadeira explosão de possibilidades e os Data Centers agarraram este oportunidade como ninguém. É claro que fazer _**cloud computing**_ em casa pode não justificar pela baixa escalabilidade, mas, para um Data Center, não há dúvidas sobre o aproveitamento máximo desta tecnologia.

_**Cloud Computing**_ é um mecanismo que permite criar uma elasticidade na capacidade de processamento, tráfego e _**storage**_ de forma automatizada. Basicamente significa que, seu precisarmos de mais um processador para dar conta de uma aplicação, por exemplo, um site de vendas cujo acesso e processamento triplicaram devido à promoção “sexta-feira negra”, o Data Center automaticamente coloca, de forma automática, mais disco e mais processadores (computadores) executando esta aplicação. A aplicação sequer precisa ser parada.

Com os hypervisors mais sofisticados, um Data Center podem sentir a necessidade de ampliação e ligar mais uma máquina virtual para atender à demanda. Atualmente e normalmente, o usuário de um serviço de _**Cloud Computing**_ percebe que precisa de mais e remotamente modifica seu perfil no cadastro do Data Center. O Hypervisor é avisado (automaticamente) da mudança e providencia a alteração automaticamente. Pelos sistemas de controle do Data Center, sem que qualquer pessoa atue, a nova cobrança pelo novo serviço já é atualizada e tudo ocorre automaticamente. A figura 3 mostra os racks de uma solução pronta para comercialização da EMC, o VCE _**clouding**_ com o produto completo VBLOCK.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/1/273150/vce_vblock_300_family_background.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/1/273150/vce_vblock_300_family_background.png)

Figura 3. Racks da solução pronta

Fonte: http://www.vce.com/

Bem, voltando ao começo, se é possível usar o máximo dos computadores físicos e apenas acionar mais servidores quando necessário, é claro que a energia total do Data Center será economizada, criando melhores condições para alcançar o Green Data Center.

**O Projeto de Data Center pensando em Cloud Computing.**

É importante perceber que o _**cloud computing**_ está crescendo muito.  Recentemente o Gartner Group estimou o gasto global com IaaS esperado de US$ 16.5 bilhões em 2015, um crescimento de 33% de 2014. É uma virada. As organizações estão chaveando seus investimentos para Cloud. Na figura 4 podemos ver a forma clássica de um data center considerando a distribuição do processamento, storage e interligações. Já na figura 5, temos a mesma situação, só que com o Data Center já preparado para cloud computing.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/8/269835/15111.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/8/269835/15111.jpg)

Figura 4. Data Center Clássico

Fonte: EMC ¿ CIS Modulo8

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/1/269140/15112.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/1/269140/15112.jpg)

Figura 5. Arquitetura para Data Center com serviços de clouding computing.

Fonte: EMC ¿ CIS Modulo8

A _**cloud computing**_ é um sistema de vários _**hardware's**_, _**software's**_ e links lógicos trabalhando juntos para levar os dados para o usuário final. Com isto em mente, as organizações devem entender como o conceito de cloud tem redefinido completamente a maneira de nós usarmos os recursos do Data Center. Alguns pontos devem ser considerados no projeto:

- **Hardware pronto para Cloud (cloud-ready)**: O Cloud Computing, gira ao redor da correta utilização dos recursos do Data Center. Por isto é importante entender bem a cloud criada para sua empresa, principalmente com o objetivo de prever expansões, que podem representar um problema depois que tudo está funcionando.
- **Controle de Dados e Segurança**: A natureza distribuída do cloud computing exige um planejamento sobre controle de dados e a infraestrutura lógica de segurança. Isto pode representar a necessidade de criar regras baseadas no usuário para sistemas de _storage_, ou colocar todas as aplicações atrás de um firewall virtual para garantir a boa fama da sua marca.
- **Transparência com o usuário final**: Todo o processo, da contratação até o uso, deve ser absolutamente claro para ambos os lados. O cliente precisa saber detalhadamente tudo que a cloud pode fornecer. É importante projetar um Data Center que permita o controle dos ambientes e possa monitor o uso do usuário de forma a prever colapsos e garantir o bom relacionamento com seu cliente.
- **Cloud Elástica**: Mais do que permitir tecnicamente a elasticidade da nuvem, é preciso projetar condições físicas e lógicas para que possíveis expansões possam ocorrer, assim como planejar o reuso de recursos que deixam de ser utilizados. Estes modelos pague pelo que você usa (pay-as-you-go), são cada vez mais difundidos e um planejamento adequado é necessário.
- **Planejamento de Capacidade**: Independente se o Data Center trabalha com cloud pública, privada ou híbrida, o planejamento de capacidade é tarefa de tempo integral. O projetista deve pensar não na demanda conhecida, mas prever o que pode acontecer para o futuro. A cloud é projetada para sediar numerosas cargas de trabalho e usuários sobre um sistema redundante. O planejamento da capacidade da cloud implementada é realmente uma tarefa sem fim, um processo contínuo de observação, monitoramento dos recursos.

Finalmente, pode-se resumir como as principais preocupações para projetar clouds no Data Center, no conjunto que segue:

- **Limitações de capacidade de infraestrutura e computadores para a cloud**. Apenas porque os recursos estão em cloud, não significa que são infinitos. Existem questões que não estão a vista, mas que podem representar grandes problemas. Por exemplo, o cliente esqueceu que no natal os acessos sobem para dez vezes o normal. Quando estiver sendo feito o planejamento, deve-se analisar quais são os recursos da cloud implantada.
- **Expansão de Infraestrutura.** O objetivo de qualquer organização é crescer e ser mais eficiente em suas práticas de negócio. Ao planejar o Data Center, deve-se entender o crescimento dos negócios dos clientes e não somente criar uma estrutura de previsão baseada no crescimento de vendas do próprio Data Center. Com os serviços de Cloud Computing, a ligação entre os negócios do cliente e a capacidade instalada do Data Center é infinitamente mais justa, isto é, mudanças nos negócios do cliente, refletem imediatamente na maneira como o cliente utiliza seus recursos de Cloud. Um sólido modelo de balanceamento e distribuição deve ser projetado.