Um projeto de Data Center começa na análise da região onde o Data Center será localizado. Entender o clima, as condições hidrográficas, trânsito, comunidade ao redor, natureza e atividades das empresas vizinhas, etc.

Algumas vezes podemos encontrar situações que implicam em risco. Veja por exemplo a situação dos Data Centers abaixo na figura 1:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/5/272592/15048.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/5/272592/15048.jpg)

Figura 1. Vista aérea de dois Data Centers.

Fonte: http://efagundes.com/blog/a-guerra-do-marketing-dos-certificados-dos-data-centers/

Observe que os dois Data Centers, fazem divisa com uma gráfica, no caso é a gráfica que produz o jornal Folha de São Paulo. Em uma gráfica existe estoque de papel e tinta.  Se ocorrer um incêndio de grandes proporções, sem contar o risco de que o incêndio rompa a capacidade de extinção do incêndio, a própria situação de acesso ao local, já coloca em risco a continuidade dos trabalhos no Data Center.

Aqui iremos apresentar alguns exemplos de projetos de Data Center. A maioria deles é apresentada como exemplo na principal norma para Data Centers, a ANSI/TIA- 942.

Na figura 2 apresentamos uma planta de data center de pequeno porte, mas já podemos identificar alguns elementos fundamentais para o bom funcionamento do data center.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/2/268297/15049.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/2/268297/15049.jpg)

Figura 2. Planta da computer room de um data center de pequeno porte.

Fonte: TIA - 942. Telecommunications Infrastructure Standard for Data Centers. Pág. 135

Algumas características são interessantes. Primeiro observe que, embora pequeno, existem 3 CRAC (_**Computer room air condiotioner**_). Por outro lado, é pequeno suficiente para usar uma MDA (_**Main Distribution Area**_), sem necessidade de criar uma HDA (_**Horizontal Distribution Area**_).

A planta está em escala tem um _**computer room**_ com cerca de 180 m2.  São dispostos na MDA, 6 racks (provavelmente com switches e _**routers**_) e 73 racks com servidores nas EDAs. Por ser um espaço pequeno, a MDA ficou de um lado da computer room. Uma posição central seria justificada para minimizar a perda dos cabos pela distância. Também, pelo mesmo motivo da MDA não ser central e não haver HDA pode-se subentender que não são equipamentos de alta densidade de cabeamento, pois os HC s estão na MDA.

Outra observação importante é que os CRACs estão corretamente instalados de frente para os corredores quentes, consegue maior eficiência por receber diretamente o ar de retorno. Como a norma recomenda, os racks são dispostos de forma a criar os corredores frios e quentes. Também notamos a ausência do NOC (_**Network Operation Center**_), visando segurança de acesso.

O próximo exemplo, apresentado na figura 3, mostra o projeto de um data center para atender múltiplos clientes corporativos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268398/15050.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268398/15050.jpg)

Figura 3. Data Center para atender múltiplos clientes corporativos.

Fonte: TIA ¿ 942. Telecommunications Infrastructure Standard for Data Centers. Pág136

Neste caso percebemos as separações de cabeamento para comunicação e energia e passam nos corredores quentes e frios conforme a norma. Quente para os cabos de comunicações e frio para os cabos de energia. Este é um data center diversificado, portanto foram distribuídos HDAs específicos para cada tipo de serviço.  A MDA está parcialmente centralizada, mas, com a quantidade de HDAs disponível, não há comprometimento das distâncias limites do cabeamento.

No exemplo da figura 4, uma planta de um IDC (Internet Data Center) com 9500 m2, com um Computer Room de 6400 m2. Neste exemplo as HDAs se dividem pelo espaço da computer room  e a MDA está localizada parcialmente central pois tem as HDAs para minimizar o efeito de distâncias longas.

Figura 4. Um Internet Data Center de grande porte.

Fonte: TIA ¿ 942. Telecommunications Infrastructure Standard for Data Centers. Pág 137

Pode-se perceber uma entrada de segurança que dá acesso ao Data Center e outra porta de acesso primário à MDA e uma sala dedicada para a SAN. Ambas as salas, MDA e SAN, possuem mais uma porta para o acesso direto a elas. Pelo aspecto geral, a MDA está fazendo papel da ER (_**Entrance room**_).

A MDA está suportada por duas PDUs e 20 racks para _**cross-connect**_ (localizados na _**computer room**_) e oferece 50 racks de acesso para fornecedores de telecom (função principal da ER) e dois CRACs. A separação em sala dedicada para SAN é importante quando o _**storage**_ é mantido por terceiros.

A _**Computer Room**_ tem 4300 racks, os quais recebem o cabeamento horizontal através de 6 HDAs para minimizar o volume de cabos abaixo do piso elevado. As HDAs são centrais às áreas que apoiam para minimizar o comprimento dos cabos. Para as áreas mais próximas da TR (_**Telecommunication Room**_) são atendidos por ela e as outras pela MDA.