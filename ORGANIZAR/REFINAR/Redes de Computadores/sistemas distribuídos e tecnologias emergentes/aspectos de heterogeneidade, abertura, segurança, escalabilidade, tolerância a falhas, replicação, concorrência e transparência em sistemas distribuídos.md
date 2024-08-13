A concorrência em Sistemas Distribuídos existe porque no ambiente de redes, cada computador é independente permitindo o trabalho simultâneo em várias máquinas.

O conceito de tempo associado à transmissão de uma mensagem é importante em sistemas distribuídos e é derivado do conceito de ordem dos eventos e é de particular interesse na solução de problemas de sincronização.

Sistemas Distribuídos possuem um projeto bastante simples, mas devemos considerar alguns itens que podem se tornar um grande desafio no seu desenvolvimento, tais como:

- Heterogeneidade;
- Abertura;
- Segurança;
- Escalabilidade;
- Tolerância a Falhas;
- Replicação;
- Concorrência;
- Transparência.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/6/302667/20538.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/6/302667/20538.png)

Eventos de um projeto de Sistemas Distribuídos

Fonte:

Então, vejamos individualmente, cada um desses itens:

**ASPECTOS DE HETEROGENEIDADE**

Sistemas Distribuídos precisam ser construídos a partir de uma variedade de diferentes fatores, tais como: vários tipos de redes, sistemas operacionais (com interfaces diferentes para os protocolos de comunicação), tipos de hardware (com diferentes representações de dados e código de maquina) e linguagens de programação (com diferentes representações de estruturas de dados).

Os protocolos de comunicação, usados tipicamente na internet e em outras redes de computadores, mascaram as diferenças entre as redes e Middleware (que fornece um modelo computacional uniforme para programadores)  e pode lidar com as outras diferenças.

Dessa forma, a heterogeneidade nos Sistemas Distribuídos deve permitir acesso a um conjunto heterogêneo de computadores e redes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/6/302666/20539.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/6/302666/20539.png)

Aspectos da Heterogeneidade

Fonte:

**ABERTURA**

A abertura é a característica que determina se um sistema pode ser ampliado e reimplementado de várias maneiras. Em redes de computadores de modo geral, ela é expressa pela flexibilidade obtida com a utilização dos protocolos de comunicação que permitem diferentes arquiteturas interagir trocando mensagens.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/5/1/315186/20540.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/5/1/315186/20540.jpg)

Abertura

Nos sistemas Distribuídos esta abertura é determinada pelo grau aos quais novos serviços de compartilhamento de recursos podem ser adicionados e ficarem disponíveis para uso por uma variedade de programas clientes.

Um Sistema Distribuído aberto é um sistema que oferece serviços de acordo com regras padronizadas que descrevem a sintaxe e a semântica desses serviços.

De uma maneira geral, os serviços são especificados por meio de interfaces que costumam ser descritas em uma Linguagem de Definição de Interface (IDL – Interface Definition Language).

Entretanto, a abertura de um sistema só é obtida se a especificação e a documentação dos softwares que definem as interfaces dos componentes do sistema forem conhecidas. Assim, estas especificações devem ser completas e neutras significando que tudo que é necessário para uma implementação foi, de fato, especificado. Além disso, deve-se ser considerado dois outros fatores:

**Interoperabilidade** que vai caracterizar até que ponto duas implementações de sistemas ou componentes de fornecedores diferentes devem coexistir e trabalhar em conjunto, com base na mera confiança mútua nos serviços de cada um, especificados por um padrão comum.

**Portabilidade** que caracteriza até que ponto uma aplicação desenvolvida para um sistema distribuído pode ser executada em outro sistema distribuído diferente que implementa as mesmas interfaces.

**SEGURANÇA**

A proteção dos recursos compartilhados é um dos grandes problemas dos Sistemas Distribuídos, uma vez que o acesso a esses recursos deve ser facilitado para atingir seu objetivo de compartilhamento.

A codificação dos dados, que é criptografada, pode prover proteção adequada na transmissão dos dados, mas ainda é difícil evitar ataques como o de Recusa de Serviço (_**Denial of Service**_ - _**DoS**_). Nestes casos, grandes quantidades de requisições sem sentido são feitas a um serviço de modo que um usuário que realmente necessita do serviço não consegue obtê-lo.

Muitas das informações disponíveis nos sistemas distribuídos têm um alto valor intrínseco para seus usuários, portanto sua segurança é consideravelmente importante.

A segurança para recursos de informação possui 3 (três) componentes:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/6/302679/20542.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/6/302679/20542.png)

Segurança da Informação

Fonte:

- **Confidencialidade**: Que trata da proteção contra revelação para pessoas não autorizadas.
- **Integridade**: Que vai cuidar da proteção contra alteração ou corrupção.
- **Disponibilidade**: Que é a proteção contra interferência em relação ao acesso, ao recurso.

**ESCALABILIDADE**

Escalabilidade é uma das mais importantes metas e um dos principais argumentos em favor dos Sistemas Distribuídos, podendo ser abordada por diferentes pontos de vista:

**Escalável quanto ao tamanho**: Podem-se acrescentar mais recursos e usuários ao sistema.

**Escalável geograficamente**: Usuários e recursos podem estar distantes uns dos outros.

**Escalável Administrativamente**: O sistema ainda pode ser fácil de gerenciar, mesmo abrangendo organizações administrativas diferentes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/5/1/315193/20544.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/5/1/315193/20544.jpg)

Escalabilidade

Um dos argumentos que levou à descentralização dos sistemas está vinculado ao fato de que sistemas fortemente acoplados possuem limitação prática no aumento do desempenho, pois necessitam de uma infraestrutura especial de barramento e memória para aumentar o número de processadores de forma que não há uma boa relação de custo e benefício.

O aumento do desempenho em sistemas informatizados encontra sua limitação na capacidade tecnológica de conectividade entre um grande conjunto de processadores. À medida que os sistemas são ampliados podem apresentar perda de desempenho devido às sobrecargas que são geradas no gerenciamento do ambiente e da solução, mas seu comprometimento pode ser impedido com uma boa arquitetura.

Um sistema cujo desempenho aumenta com o acréscimo de hardware proporcionalmente à capacidade acrescida é chamado escalável.

Projetar um sistema distribuído escalável apresentará diversos desafios:

**a)** _**Custo dos recursos físicos**_: à medida que a demanda do sistema cresce, deve ser possível acrescer os recursos a um custo razoável.

**b)** _**Perda de desempenho**_: com o crescimento do sistema a quantidade e distribuição dos recursos devem aumentar, porém isso não pode gerar uma maior complexidade no gerenciamento dos mesmos ou causará considerável redução do desempenho.

**c)** _**Prevenção da falta de recursos**_: com o crescimento dos sistemas informatizados (vide internet e computação ubíqua) é muito difícil fazer uma previsão das necessidades de recursos em longo prazo.

**d)** _**Gargalos no sistema**_: se um determinado recurso for muito requisitado, a tentativa de utilização poderá causar um gargalo de desempenho no sistema.

**TOLERÂNCIA A FALHAS**

Tolerância a Falhas é a capacidade de o sistema sobreviver à falha de alguns dos seus elementos e está associado intimamente à transparência de falhas, confiabilidade e disponibilidade do sistema.

Em Sistemas Distribuídos, espera-se que a falha de um componente do sistema não afete de maneira significativa a tarefa que está sendo realizada, isto é, pode haver perda de desempenho, mas a tarefa é realizada.

Questões sobre o efeito de uma falha no sistema são as mais difíceis de responder e sanar e dependem dos objetivos do sistema, bem como de sua estrutura de recursos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/8/292886/18085.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/8/292886/18085.png)

Tolerância a Falhas

Tipicamente obtém-se a Tolerância a falhas com a redundância de hardware e software.

Se as características de transparência forem atingidas, é possível migrar um recurso de hardware e software de um sistema para outro que esteja disponível sem o conhecimento do usuário.

A técnica para tratar esse problema é detectar a falha e se utilizar das técnicas de redundância de hardware e recuperação por software.

**REPLICAÇÃO**

Trata da duplicação de recursos de um elemento processador em outro.

O “_**Método de replicação da cópia principal”,**_ determina inicialmente qual das cópias replicadas irá ser a principal. O acesso de leitura poderá ser realizado em qualquer uma das cópias, porém o acesso para atualização somente será efetuada na cópia principal.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265251/13841.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265251/13841.jpg)

Exemplo de Replicação/Duplicação

**CONCORRÊNCIA**

Um dos grandes atrativos dos Sistemas Distribuídos é a possibilidade de compartilhar recursos de serviços e aplicativos. Este compartilhamento abre a possibilidade de que um determinado recurso tente ser acessado por vários clientes ao mesmo tempo, como por exemplo, o acesso aos lances em um leilão (mercado livre, e-bay, etc...) que chega ao limite de tempo.

Limitar o recurso compartilhado a um cliente por vez resolve o problema de concorrência, mas também limita a produção do sistema o que não é desejado.

Usualmente Sistemas Distribuídos permitem o acesso concorrente dos recursos, porém é comum utilizar objetos encapsulados que assumam a responsabilidade de alguma estrutura de sincronização.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/5/2/315200/20545.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/5/2/315200/20545.jpg)

Concorrência em Sistemas Distribuídos

**TRANSPARÊNCIA**

Uma das principais necessidades dos Sistemas Distribuídos é tornar o ambiente de rede invisível provendo a visão de um ambiente único para o usuário.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/5/2/315201/20547.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/5/2/315201/20547.jpg)

Transparência em Sistemas Distribuídos

Para Tanenbaum (2007), um Sistema Distribuído que é capaz de se apresentar a usuários e aplicações como se fosse um único sistema de computador, é denominado transparente.

O objetivo da transparência é tornar certos aspectos da distribuição invisíveis ao programador de forma que ele precise se preocupar apenas com o projeto de sua aplicação particular.

O usuário não deve ter conhecimento da distribuição de recursos do sistema, portanto é importante ocultar o fato de que os processos e demais recursos estão fisicamente distribuídos.

Desta forma, não é necessário se preocupar com o local onde uma aplicação está instalada ou os detalhes de como suas operações serão acessadas por outros componentes.

Assim, os recursos que não são diretamente relevantes para a execução de uma tarefa de interesse num determinado instante são escondidos e passam anônimos através da transparência.

É fácil perceber que, apesar das vantagens, a transparência nem sempre é desejada. Veja o caso em que o usuário necessita, por exemplo, de um documento impresso. É usual que o trabalho seja executado em uma impressora próxima ao usuário, sendo mais conveniente deixar que o usuário faça a escolha dessa impressora. Na prática, um sistema transparente oculta alguma informação do usuário ou dos processos.

Vejam os tipos de transparências reconhecidos pela _**International Organization for Standardization**_ (ISO) de 1995:

**Acesso** à Oculta diferenças na representação de dados e no modo de acesso.

**Localização** à O local do recurso é desconhecido.

**Migração e Relocação** à O recurso pode ser movido, inclusive enquanto está em uso. **Replicação** à Múltiplas instâncias de um recurso podem ser utilizadas para aumentar confiabilidade e desempenho sem o conhecimento destas réplicas.

**Concorrência** à Vários usuários pode compartilhar o mesmo recurso.

**Falha** à A falha e a recuperação de um recurso não pode afetar o sistema.

Alguns outros tipos podem ser considerados conforme o ponto de vista aplicado pelo estudioso, como a transparência de Desempenho ou Mobilidade dada por Coulouris (2001).