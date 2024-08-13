### Introdução a Padronização

Em comunicação de dados, a comunicação ocorre entre entidades. As **entidades** são qualquer coisa ou dispositivo capaz de enviar ou receber informação. Entretanto, uma entidade não pode enviar informações para outra entidade de qualquer forma, sem antes saber se a entidade receptora será capaz de compreender. Para que ocorra a comunicação é necessário estabelecer um protocolo entre as entidades. Um protocolo, segundo (Forouzan, B. A, 2007), "é um conjunto de regras que controla a comunicação de dados. Um protocolo define o que é comunicado, como isso é comunicado e quando deve ser comunicado".  Os elementos básicos de qualquer protocolo são descritos abaixo:

- **Sintaxe:** a sintaxe refere-se à estrutura ou o formato dos dados, correspondendo à ordem com que os dados devem ser apresentados. Por exemplo, um protocolo qualquer poderia esperar que os primeiros 48 bits significassem o endereço de destino, o segundo conjunto também de 48 representam o endereço de origem da mensagem, e por sua vez, os bits restantes representam a mensagem propriamente dita.
- **Semântica:** a semântica corresponde ao significado de cada conjunto de dados apresentados anteriormente. Os primeiros 48 bits correspondem ao endereço de origem ou de destino? Conhecendo a semântica, sabe-se como padrão deve ser interpretado e qual ação que deve ser tomada.
- **Sincronização da comunicação (timing):** Deve existir, entre o transmissor e receptor, uma negociação prévia estabelecendo quando os dados devem ser enviados e a quantidade de dados que o receptor é capaz de receber. Por exemplo, um transmissor produz dados a uma taxa de 100Mbps (Megabits por segundo), mas o receptor é capaz de receber a uma taxa de 10Mbps. Caso isso ocorra, o receptor ficaria sobrecarregado.

### Padrões

Existem, atualmente, diversos fabricantes de rede, cada um com sua própria ideia de como deve ser feito um determinado equipamento. Sem os padrões utilizados pelas indústrias para a fabricação de um determinado dispositivo, poderia haver um caos nas comunicações de dados como, por exemplo, um fabricante A poderia estabelecer um padrão para transporte de dados incompatível com o fabricante B. Para evitar esse tipo de problema, os padrões são desenvolvidos visando permitir a inteconectividade nas comunicações nacionais e internacionais a partir do estabelecimento de diretrizes que devem ser seguidas pela indústria e órgãos governamentais. Existem basicamente duas categorias de padrões que são descritas a seguir:

- **De jure:** ao contrário do de fato (em português ?por lei?), o de jure são padrões legais e formais adotadas por uma instituição de padronização autorizada, tais ISO (International Standard Organization - Organização Internacional de padronização) e ABNT (Associação Brasileira de Normas Técnicas) (Tanenbaum, A. 2011). Um típico exemplo de jeru é arquitetura OSI (Open systems interconection - modelo aberto de interconexão de redes) desenvolvido pela ISO, mostrado na Figura 1, tendo como objetivo se tornar um padrão aberto para comunicação em redes de computadores.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/8/262845/10829.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/8/262845/10829.jpg)

Figura 1 - Modelo OSI - Um padrão de jure estabelecido pela ISO.

- **De facto:** os padrões de facto (em português “de fato”) correspondem a aqueles padrões que se consagraram naturalmente, por possuírem grande aceitação Um exemplo típico de um padrão de facto é o IBM PC (Figura 2) e seus sucessores, que se tornaram padrões para computadores pessoais e de escritórios por dezenas de fabricantes de computadores (Tanenbaum, A. 2011). É importante salientar que um padrão de facto pode ter seu status alterado para de jure por uma organização de padronização.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/2/3/362375/27768.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/2/3/362375/27768.png)

Exemplo de um padrão de facto: IBM PC lançado em 1981.

Fonte: IBM PC 5150. Autor: Ruben de Rijcke .Disponível em: [**Wikimedia.**](https://tr.m.wikipedia.org/wiki/Dosya:Ibm_pc_5150.jpg)

### Organizações de padronização

Os padrões surgem a partir de cooperação entre órgãos governamentais reguladores, indústria e comitês de criação de padrões (Forouzan, B. A, 2007). Devido a grande quantidade de organismos de padronização, podemos classifica-los de acordo com a sua abrangência geográfica (nacional e internacional) e organizações para padrões profissionais, comerciais e industriais, como descrito abaixo:

**Organizações para padrões nacionais:** Em cada país, existem instituições sem fins lucrativos com o objetivo de estabelecer os padrões locais, normalmente, em consonância com organismos internacionais como, por exemplo, a ISO. Algumas dessas organizações são descritas abaixo:

- **ABNT** Associação Brasileira de Normas Técnicas: A ABNT é uma entidade privada sem fins lucrativos, membro fundador da ISO, da Comisión Panamericana de Normas Técnicas (Comissão Pan-Americana de Normas Técnicas - Copant) e da Asociación Mercosur de Normalización (Associação Mercosul de Normalização - AMN).Também é membro desde a fundação da International Electrotechnical Commission (Comissão Eletrotécnica Internacional - IEC). É responsável pelas Normas Brasileiras (ABNT NBR) (ABNT, 2016).
- **ANSI** - American National Standards Intitute (Instituto americano de padrões nacionais): Organização privada sem fins lucrativos e não afiliado ao governo americano.
- **BSI** – British Standards Institute (Instituto inglês de padrões): Semelhante aos anteriores estabelece padrões técnicos de produtos e serviços.
- **DIN** – Deutsches Institut for Normung (Instituto alemão de normas): A DIN estabelece padrões técnicos de produtos e serviços para a comunidade alemã.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/2/4/362458/27954.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/2/4/362458/27954.png)

Novo padrão de tomada e plug definido pela ABNT NBR 14136

**Organizações para padrões internacionais:** As principais organizações de padronização mundialmente aceitas são descritas abaixo:

- **ISO** – International Standards Organization (organização internacional de padrões): Um dos principais organismos de padronização internacional. A ISO é um comitê multinacional formado por associados de organizações para padronização nacional. Em redes de computadores, como já comentado, estabeleceu o modelo OSI como um padrão aberto de comunicação, mostrado na Figura 1.
- **ITU-T** – International Telecommunications Union (união internacional de telecomunicações): Comitê dedicado à pesquisa e estabelecimento de padrões de comunicação de dados e telefonia. Os padrões de compactação digital ITU-T – H.261 e H.263 são exemplos dos padrões desenvolvidos por esta organização.

**Organizações para padrões industriais, comerciais e profissionais:** As associações abaixo são formadas, principalmente, por profissionais de engenharia e indústria:

- **EIA** – Electronic Industries Association (Associação das indústrias eletrônicas): É uma organização sem fins lucrativos dedica a promoção de questões de fabricação eletrônica.
- **TIA** – Telecommunication Industries Association (Associação das indústrias de telecomunicações): A TIA é uma associação que representa os principais desenvolvedores de produtos e serviços de telecomunicações e é credenciada ANSI. A ANSI, EIA e TIA possuem muitos padrões em comum como, por exemplo, o cabeamento par trançado para redes de computadores (Figura 5).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/8/270854/14971.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/8/270854/14971.jpg)

Figura 5 - Cabeamento par trançado definido pelas organizações ANSI/TIA/EIA.

- **IEEE** – Institute of Electrical and Electronic Engineers (Instituto de engenheiros elétricos e eletrônicos): É a maior associação mundial de profissionais da engenharia do mundo. O IEEE tem como objetivo proporcionar o desenvolvimento científico e tecnológico nas áreas de engenharia elétrica, eletrônica e informática. Tem como um de seus objetivos supervisionar o desenvolvimento e a adoção de padrões na área de computação e comunicação de dados.
- **IETF** – Internet Engineering Task Force (grupo de trabalho de engenharia da Internet): Instituição internacional que promove as normas da Internet, estabelecendo as especificações de protocolos utilizados na Internet. O detalhamento de cada protocolo utilizado na Internet é divulgado por meio de documentos chamados de **Request for Comments (RFC)** ("pedido de comentários"). Por exemplo, os RFCs 793 e 2616 estabelecem especificações para implementação dos protocolos TCP e HTTP, respectivamente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/2/5/362548/27961.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/2/5/362548/27961.png)

Figura 4 - Padrões IEEE para comunicação de dados.