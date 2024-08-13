No projeto de Data Centers outro aspecto que deve ser considerado é como se dá a distribuição dos diversos cabos em seus respectivos espaços diferenciados no Data Center e quais são os tipos  de cabeamento para cada funcionalidade e suas respectivas interfaces.

Neste material, será utilizada, como referência e nomenclatura, a norma TIA 942. A seguir vamos definir os espaços e a nomenclatura dos elementos que compõe o sistema de cabeamento.

A figura 1 mostra a base de um Data Center em termos de elementos funcionais e seus espaços.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/7/260763/14966.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/7/260763/14966.jpg)

Figura 1: Elementos funcionais de um Data Center e seus espaços

Fonte: Figura adaptada da norma 942. Já utilizada aqui no tópico 2, figura 2.

Cada espaço no Data Center tem a função de sediar um conjunto específico de equipamentos, concentrar funcionalidade e distribuir, desde a alimentação de energia, controles e dados. Aqui, em se tratando de cabeamento, interessam os espaços e elementos que são responsáveis pela distribuição dos serviços de telecomunicações, comumente chamados de Distribuidores de Telecomunicações. Portanto, é importante rever quais são estes espaços e elementos e como eles são divididos pela visão dos subsistemas de cabeamento existentes no Data Center. Segue a lista de elementos e o relacionamento com os subsistemas de cabeamento.

**Espaços:**

- _Telecommunications entrance room_ (**TER**): Também conhecido apenas como _Entrance Room_ (ER). Sala de Entrada de Telecomunicações.
- _Main Distribution Area_ (**MDA**): Área de Distribuição Principal.
- _Intermediate Distribution Area_ (**IDA**): Incluído pela norma TIA 942-A, Área de Distribuição Intermediária.
- _Horizontal Distribution Area_ (**HDA**): Área de Distribuição Horizontal.
- _Zone Distribution Area_ (**ZDA**): Área de Distribuição de Zona.
- _Equipment Distribution Area_ (**EDA**): Área de Distribuição de Equipamentos.

**Interconexões (sua localização):**

- _External Network Interface_ (**ENI)**: Interface de rede externa. Dentro do **TER**. Como no TER todos os sistemas externos de telecomunicações entram no Data Center, isto é, os cabos que saem para a internet, rádios de _backbones_ externos de telecomunicações, links vindos de clientes, etc., precisa haver uma interface ou uma interconexão com o cabeamento estruturado do Data Center chamada **ENI.**
- _Main Cross-connect_ (**MC**): Interconector Principal. Dentro da **MDA**. A MDA é o ponto central de distribuição do cabeamento estruturado e, por tal razão, muitas vezes, pode fazer o papel do TER. A tarefa física de realizar a distribuição é executada pelo MC.
- _Intermediate Cross-connect_ (**IC**): Interconector Intermediário. Dentro da **IDA**. A IDA pode ser localizada em uma posição central para minimizar os problemas de comprimento de cabos. Isto é mais fácil quando o Data Center trata apenas de uma empresa. No caso de um Data Center com múltiplos clientes, a IDA certamente precisa estar em uma sala separada com todos os requisitos de segurança necessários. O papel de interconectar hierarquicamente o cabeamento estruturado é executado neste ponto, portanto neste espaço (IDA) estão localizados _switches_ ( LAN, SAN, console e gerenciamento). Frequentemente pode-se encontrar HCs dentro das IDAs para atenderem armários e racks próximos.
- _Horizontal Cross-connect_ (**HC**): Interconector Horizontal. Dentro do **HDA**. Este equipamento tem como função produzir as terminações das ligações com os armários e racks recebendo os cabos que chegam das EDAs. Na HDA encontram-se switches da mesma forma que os IDAs. Existe uma recomendação de existir pelo menos um HC por andar. **Ele pode estar localizado na MDA, IDA ou HDA**. O posicionamento do HC também é uma escolha para evitar a limitação de comprimento do cabeamento de _backbone_, portanto é posicionado equidistante dos equipamentos para os quais ele distribui cabos. No caso da HDA possuir sua própria sala, recomendado em Data Centers com múltiplos clientes, também se recomenda um HVAC (sistema de climatização) e painéis técnicos próprios. Para fins de redundância, é comum os racks serem conectados a duas HDAs.
- _**Zone Outlet**_ ou _Consolidation Point_ : Ponto de Concentração de Tomadas/Saídas. Dentro do **ZDA**. Este equipamento consolida o cabeamento horizontal. Dependendo do porte e tipo de Data Center, pode consolidar ou concentrar as EDAs ou, diretamente, os EOs. A norma recomenda um máximo de 288 cabos UTP ou Coaxiais para evitar congestionamento. Os _Zone Outlet's_ têm a função de organizar e agrupar o cabeamento horizontal, concentrando grupos de EDAs para as MDAs, IDAs ou HDAs, como mostra a figura 2.
- _Equipment Outlet_ (**EO**): Tomada de Equipamento. Dentro da **EDA**. A EDA é o local onde o cabeamento horizontal termina e dispõe-se em tomadas ( EOs) onde os equipamentos de telecom são conectados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/7/260779/14967.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/7/260779/14967.jpg)

Figura 2 : Distribuição do cabeamento horizontal em relação aos espaços correlatos do Data Center.

Fonte: Autoria própria

**Subsistemas de Cabeamento:**

- **Cabeamento de Backbone:**
    - Cabeamento que faz a ligação entre o TER e os MDAs, osIDAs e os HDAs.
    - Cabeamento que faz a ligação entre o MDA e os IDAs e os HDAs.
    - Cabeamento que faz a ligação entre os IDAs e os HDAs.
- **Cabeamento Horizontal:** Cabeamento da ZDA. São os cabos que ligam os racks e armários aos concentradores ou organizadores.

_**O backbone**_ é o cabeamento que interliga os distribuidores, diferente do que o leitor pode pensar, uma vez que este termo é usado para definir a rede ou malha principal de um provedor. Este _**backbone**_ tem o objetivo mais importante do que simplesmente interligar os armários (na literatura técnica internacional chama-se “cabinet”), seu objetivo é garantir disponibilidade através de interligações que refletem em redundância. Para o administrador de redes, embora o assunto “cabeamento estruturado” não seja o foco principal, a redundância garantida pelos MDAs, HDAs e IDAs, vem de conexões duplicadas e, principalmente, se switches e roteadores em topologia cross-connect. Em Data Centers, os routers e switches têm sempre uma forma de trocar o caminho, em caso de falhas, para outros caminhos e isto é feito com duplicação de equipamentos ativos de rede.

O cabeamento horizontal é o conjunto de cabos que encontramos embaixo do piso, ou, na minoria das situações, acima do forro. Estes cabos conectam os racks e armários com os MDAs, HDAs, e IDAs. É uma hierarquia de conexões, bem representada na figura 2.

**Sistemas de Cabeamento**

O sistema de cabeamento de telecom é essencial para garantir a disponibilidade das aplicações de TI e no Data Center. Sem um sistema de cabeamento de alta performance seria impossível a comunicação entre os servidores, o _**storage**_ e outros equipamentos para trocar, processar e armazenar dados. Os requisitos para que o cabeamento acompanhe o nível de disponibilidade e performance atuais são:

- Canais de alta densidade.
- Velocidades altas de transmissão.
- Mudanças de hardware sem interrupção.
- Aspectos de ventilação.
- Suporte.

A importância do cabeamento em um Data Center é tão grande, que as normas de transparência para negócios de empresas como os bancos e financeiras, exigem a documentação completa das escolhas, projetos e execução do cabeamento.

Devido aos requisitos de máxima disponibilidade e o crescimento da taxa de transmissão e a demanda de qualidade sobre os componentes do cabeamento para Data Centers, eles são considerados mais altos (complexos e sofisticados) que os componentes para os produtos destinados a redes LAN (_**Local Area Network)**_. Garantir a alta qualidade significa planejar antes de tudo quais os sistemas de cabeamento a serem utilizados. Procura-se, na fase de projeto, encontrar os seguintes requisitos ou características dentro dos aspectos abaixo listados:

- Sistemas de cabeamento com proporções planejadas de cobre e fibra óptica.
- Capacidade de largura de banda dos sistemas de cobre e ópticos.
- Perdas de inserção e retorno de fibras óticas. (_loss budget_)
- Imunidade a problemas de compatibilidade eletromagnética (EMC _immunity_)
- Capacidade de migração para um estágio mais avançado de classe de velocidade.
- Projeto dos armários (_cabinet_) e racks.

Devem ser consideradas redundância e confiabilidade além de completa capacidade de instalação por parte dos executores do projeto. Cabos encomendados de fábrica trazem melhor garantia.

**Documentação e Rótulos.**

Um requisito essencial para a boa administração do sistema de cabeamento, é o planejamento adequado, meticuloso e a atualização contínua da documentação. Existem muitas planilhas em Excel para este planejamento além de softwares especializados. É fundamental que a situação atual do sistema de cabeamento esteja totalmente refletida na documentação.

Os rótulos utilizados devem representar uma identificação unívoca, isto é, não pode haver qualquer situação de existirem dois rótulos representando cabos diferentes. Os rótulos precisam estar em posições de fácil acesso e leitura. Estes rótulos devem seguir uma regra bem definida. Podemos utilizar softwares com esta capacidade de controle.

**Fibras Óticas.**

O entendimento de fibras óticas e suas características de transmissão e disposição física, condições de instalações, como ângulos máximos, tensão admissível, conexão, etc., é da competência de outra disciplina.

Este material visa a compreensão de como os cabos óticos podem influenciar e modificar a execução e os projetos de Data Center. A recomendação para as redes de alta performance é Multimode Fiber com OM4.

Dois parâmetros são os principais delineadores dos projetos de Data Center, no que concerne a fibras óticas. São eles: _**Power Budget**_ e _**Loss Budget**_ (em uma tradução livre: Potência Orçada e Perda Orçada).

**Power Budget**

_**Power Budget**_ refere-se à quantidade de perda que o link de dados (do transmissor até o receptor) pode tolerar permanecendo em funcionamento. Algumas vezes aparecem vinculados a este parâmetro um valor mínimo e um valor máximo. Este valor mínimo significa um valor tal que a potência de saída do transmissor não sobrecarregue o receptor. O valor máximo refere-se a um valor cujo excedimento provocaria queda de link por falta de sinal em relação à sensibilidade do receptor. Os _**datalinks**_ (links de dados) são limitados pelo _**power budget**_ do link. Na prática, o _**power budget**_ é a diferença entre a potência de saída do transmissor e a potência **requerida** de entrada do receptor. Observe que a palavra “requerida” foi grifada. Isto quer dizer: Não medimos a saída e a entrada. Estamos falando de quanto é tolerado de perda no datalink, já sabendo dos dados do fabricante dos equipamentos. A Figura 3 demonstra como as perdas são consideradas para se planejar ou projetar o cabeamento no data center, além de mostrar como as perdas se somam e a relação entre as perdas ocorridas e a margem de segurança do projeto. Em termos de compras, é claro que precisamos pensar no projeto como um todo para entender como devem ser os equipamentos coerentemente com os cálculos. A distância entre as MDAs, EDAs, IDAs, etc., torna-se importante neste momento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/4/265458/14968.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/4/265458/14968.jpg)

Figura 3. Power Budget. Uma comparação da composição das perdas e margem de projeto

Fonte: Autoria própria

_**Loss Budget**_

_**Loss Budget**_ refere-se à quantidade de perda que o cabo óptico poderia ter. Ele é calculado pela soma das perdas em todos os componentes associados ao link desde seus conectores, a fibra propriamente e a distância (atenuação), para resultar na perda estimada fim-a-fim (end-to-end loss). O objetivo de se ter este valor é suportar dois momentos importantes: 1) Durante o projeto para certificar que o cabo escolhido será adequado e; 2) Depois da instalação, a comparação da perda calculada com o resultado dos testes para verificar se a instalação foi feita corretamente.

É claro que precisamos pensar nas distâncias em termos de projeto e ainda no tipo de fibra e o comprimento de onda a ser utilizado nos links e nas interfaces, respectivamente. A figura 4 apresenta a organização do cabeamento óptico em um rack de alta densidade.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/8/260806/14969.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/8/260806/14969.png)

Figura 4. Organização de chegada e conexão do cabeamento óptico de alta densidade

Fonte: http://portal.furukawa.com.br/arquivos/Guia%20de%20Aplica%C3%A7%C3%A3o%20Data%20Center%202015/guia-de-aplicacao-data-center-2015.pdf pág. 48

**Cabos de Cobre.**

Atualmente o cabeamento de um Data Center está distribuído de forma que 50 % está sendo coberto por fibra ótica e 50% cabos de cobre. A frequência de fibra em um Data Center reflete em uso em SAN _**(Storage Area Network**_) com o protocolo dominante _**FIBRE CHANNEL**_. O protocolo ETHERNET tem seu principal papel na ligação com a rede local (LAN).  Comparativamente o cabeamento de cobre tem seus dias contados já que o TCO (_**Total Cust Ownership**_ – Custo total de propriedade) da fibra é menor.

É recomendado para o cabeamento de cobre, no caso do subsistema de cabeamento horizontal, um mínimo de categoria 6A pela norma, mas, com a tendência de unificar a rede de fibra da SAN com a LAN, a categoria 7A já está considerada como recomendação, para par balanceado (_**balanced-pair**_).

O cabeamento de cobre está, atualmente, no estado de arte desta tecnologia, as soluções comerciais suportam 10 Gb/s Ethernet e são confiáveis até 100 metros (10GBASE-T).

Outra situação que deve ser considerada é a expansão de fogo pelo uso de cabos de cobre. A recomendação é para o tipo de construção LCC (teflon como componente principal das capas). Também o LSZH (_**Low-smoke halogen-free**_) é recomendado na Europa. Apesar destes cabos queimarem, não geram fumaça tóxica.

Independente de qualquer questão, o cabeamento horizontal, notadamente entre switches e servidores, tem sido o cabeamento de cobre Categoria 6A e caminhando para Categoria 7A. A estrutura de um cabo como estes citados está na figura 5.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/8/260846/14970.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/8/260846/14970.jpg)

Figura 5: Apresenta a composição de um cabo de rede de cobre.

Fonte: Autoria própria

A figura 6 apresenta um rack com os sistemas de organização para chegada e conexão do cabeamento de cobre.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/8/270854/14971.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/8/270854/14971.jpg)

Figura 6: Vista de patch panel. (cabos para 10GBASE-T)

Fonte: Shutterstock 225505258

A junção da SAN com LAN agregando maior facilidade de implementação e gerenciamento está levando rapidamente para um padrão ethernet. O Cabeamento de cobre pode crescer mais ainda, especialmente com a padronização da categoria 7A, cujos componentes de implementação já são pensados para alta densidade, proteção contra incêndio, alta performance e ocupação melhorada de espaço. Maiores informações especificas e detalhadas podem ser encontradas na norma TIA 568-C, cujas inovações já se encontram na norma TIA 942-A.