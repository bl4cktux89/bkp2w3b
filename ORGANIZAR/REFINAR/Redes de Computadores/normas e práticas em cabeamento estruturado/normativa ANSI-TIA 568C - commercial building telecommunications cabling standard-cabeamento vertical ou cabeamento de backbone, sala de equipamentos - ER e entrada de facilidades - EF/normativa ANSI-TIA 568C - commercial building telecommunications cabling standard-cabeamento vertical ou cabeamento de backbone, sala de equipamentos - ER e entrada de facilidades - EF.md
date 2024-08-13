**Introdução**

O cabeamento de backbone é responsável pela interligação entre os diversos TR dentro do mesmo prédio e pela interligação entre os prédios em caso de redes instaladas em campus.

Como já foi discutido nas aulas anteriores, em todos os TR existe a presença do _**cross-conect**_, que é responsável pela interligação do cabeamento horizontal com o backbone.

Por sua vez, o backbone está diretamente conectado à sala de equipamentos (ER), onde se encontram os principais equipamentos de tratamento da informação: servidores, centrais telefônicas do tipo PABX, hardwares mais complexos de interligação (rádios, modems, multiplexadores etc.), e nessa sala há o principal _**cross-connect**_, chamado de Main Cross-Connect (MC), de onde partem as principais ligações para todo o complexo de rede em tecnologia de cabeamento estruturado.

Outra categoria é o Intermediate Cross-Connect (IC), que corresponde a um nível intermediário, mais complexo que o horizontal, porém não sendo o principal. A topologia empregada é a Estrela Hierárquica.

**Cabeamento vertical – backbone**

Tendo em vista perdas no sinal em decorrência da distância dos cabos lançados, as normativas consideram que não pode haver mais do que dois níveis hierárquicos de _**cross-connect**_, ou seja, do MC tem-se ligações diretas para IC e HC e dos IC para HC. Para o cabeamento de backbone, existem meios de transmissão homologados, que são:

- Cabo UTP (_Unshielded Twister Pair_) de quatro pares, 100 ?.
- Cabo F/UTP (_Foiled Unshielded Twister Pair_) de quatro pares, 100 ?.
- Cabo UTP multipares categoria 5e.
- Cabo telefônico do tipo CI – Cabo Interno.
- Cabo óptico multímodo 62,5/125 µm ou 50/125 µm.
- Cabo óptico monomodo.
- Cabo telefônico do tipo CTP-APL – Cabo Externo.

Veja o desenho abaixo que ilustra todos os componentes que montam um cabeamento vertical utilizado em um edifício, bem como um backbone horizontal utilizado em um campus com todos os componentes citados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/6/104601/a09i01_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/6/104601/a09i01_cabestru80_100.jpg)

As normativas também definem o comprimento máximo de todos os cabos homologados na configuração de backbone primário e secundário, conforme ilustra a tabela na sequência.

![[Untitled 55.png|Untitled 55.png]]

Em termos de tecnologia atual, quando um cabo UTP for transportar sinais digitais há um limite de 90 metros a ser observado, pois 800 metros atenderiam somente aplicações de voz (telefonia).

Por uma questão de cultura técnica adotada no Brasil, para o atendimento da distribuição dos sinais de voz utilizam-se os cabos telefônicos padrão TELEBRAS do tipo CI (Cabos Internos) no número de pares necessários e, no HC, deve-se manobrá-los para o cabeamento horizontal correspondente.

Os cabos de fibra óptica e de par trançado devem seguir as normas de retardância à chama para evitar a propagação de incêndios. No backbone, em que os cabos atravessam vários andares, devem-se utilizar cabos do tipo Riser (CMR), que são recomendados para aplicações verticais em poços de elevação (_**shaft**_) e em instalações nas quais os cabos ultrapassem mais de um andar.

**Percursos para o cabeamento vertical – backbone**

Definem-se como dutos de passagem que suportam e protegem o cabeamento de backbone que interliga as salas de telecomunicações (TR) à sala de equipamentos (ER), de entrada conhecida como _**entrance facility**_ (EF), ou ainda as interligações entre edifícios em um campus.

São compostos por dutos, conexões, fendas e bandejas. Como os percursos verticais realizam conexões entre andares, deve-se ter uma preocupação muito grande com o bloqueio de propagação de chamas nessas interligações.

Como a EIA/TIA 569A determina o uso de uma sala de telecomunicações por andar, e elas normalmente ficam umas sobre as outras, basta efetuar aberturas nas lajes entre os pavimentos e o percurso vertical estará montado, criando assim um poço de elevação ou simplesmente um _**shaft**_.

A EIA/TIA 569A detalha como devem ser feitas essas aberturas, propondo duas soluções, a saber: a utilização de dutos de passagem (_**sleeves**_) ou aberturas de passagem (_**slots**_).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/6/104603/a09i02_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/6/104603/a09i02_cabestru80_100.jpg)

**Sala de equipamentos – ER (**_**equipament room**_**)**

É o espaço destinado para alocação dos equipamentos principais de telecomunicações; nela ficam centralizados equipamentos como servidores de rede, central telefônica do tipo PABX, roteadores, CORE _**switches**_, modems, centrais de alarme, centrais de CFTV (Circuito Fechado de Televisão) etc.

A sala de equipamentos deverá ter área mínima de 14 m², sendo localizada estrategicamente dentro do edifício, prevendo as conexões com todas as salas de telecomunicações (TR) dos andares e com as entradas, além do acesso das pessoas de gerenciamento e manutenção.

Abriga o Main Cross-Connect, o Intermediate Cross-Connect e o Horizontal Cross-Connect do andar a que pertence.

Alguns cuidados devem ser tomados para a melhor escolha do local, são eles:

- Ser afastado de fontes de EMI (Interferência Eletromagnética).
- Possuir fácil acesso para a entrada de novos equipamentos.
- Deve possuir sistema de condicionamento da rede elétrica (_no-break_ e estabilizadores) em área separada do ER.
- Deve ter condições controladas de temperatura, umidade e poeira.
- Estar situado na posição central em relação ao edifício.
- Devem ser observadas normas relativas aos fornecedores de serviços externos referentes ao acesso.
- Controle de acesso a pessoas não autorizadas.
- Sistema de segurança e CFTV.
- Utilização de piso elevado nessas dependências.
- Equipamentos elétricos devem ser alojados em sala própria e não no ER.
- Na sala de equipamentos só é permitido quadro elétrico com disjuntores para corte e controle do local.

Para determinar o tamanho da sala de equipamentos, é necessário multiplicar o número de áreas de trabalho por 0,07 m², sendo que para locais com menos de 200 áreas, considera-se o tamanho de 14 m². A tabela a seguir exemplifica o tamanho de salas de equipamentos para algumas quantidades específicas:

![[Untitled 1 38.png|Untitled 1 38.png]]

Dimensionamento da sala de equipamentos.

Para alocação dos equipamentos e do sistema de cabeamento estruturado, são utilizados racks padronizados de 19" (polegadas) com diferentes alturas.

As alturas dos racks são medidas em UA (Unidade de Altura), e cada UA tem exatamente 44,45 mm. Essa medida permite aos fabricantes padronizar todos os produtos e equipamentos utilizados em sistemas de cabeamento estruturado e informática.

Como exemplo, todos os equipamentos ativos de rede, como os _**switchs**_ e roteadores, bem como _**patch panel**_ e demais produtos que são instalados em racks, têm suas medidas baseadas na UA.

Os racks podem ser encontrados desde 10 UAs até 44 UAs de altura nos modelos rack fechado e rack aberto ou torre.

No link abaixo, veja a figura que demonstra os dois modelos de racks utilizados nas salas de equipamentos e nas salas de telecomunicações, bem como uma estrutura completa de racks instalados em um Data Center.

Em uma sala de equipamentos, podemos encontrar os dois tipos de racks, sendo que o fechado é mais apropriado para abrigar servidores, e os modelos abertos ou torre para abrigar o sistema de cabeamento, pois esses modelos poderão vir com guias verticais de gerenciamento, sendo totalmente acoplados em mais racks, formando paredes de racks de acordo com a densidade de pontos instalados. Veja a figura abaixo que ilustra uma sala de equipamentos com os racks de cabeamento acoplados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/6/104608/a09i04a_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/6/104608/a09i04a_cabestru80_100.jpg)

**Entrada de facilidades – EF (**_**entrance facility**_**)**

As instalações de entrada no edifício podem ser localizadas dentro da sala de equipamentos ou em espaço próprio de acordo com o tamanho do projeto e das exigências da concessionária local de telecomunicações e dos serviços fornecidos.

Nessa entrada, considera-se a chegada do cabo da companhia telefônica, dos cabos provenientes de sistemas de antenas (satélite, micro-ondas), TV a cabo e o cabeamento de backbone vindo dos demais prédios que constituem o campus.

Deve-se considerar a possibilidade de entradas duplicadas no caso de instalações especiais que necessitem de continuidade dos serviços, por exemplo: aeroportos, hospitais, bases militares, serviços de polícia e bombeiros, centros de computação e telecomunicações.

Considerações de projeto:

- Deve ser providenciado um sistema de proteção e aterramento adequados, para evitar que induções eletromagnéticas ocorridas nos cabos externos venham causar danos pessoais e materiais ao prédio.
- Todos os cabos que possuem malha de aterramento deverão ser aterrados.
- Nos cabos geleados de fibra ou metálicos, deverá ser providenciada a contenção da geleia e a transição para cabos internos não propagarem a chama, utilizando para isso caixas de emendas ou distribuidor interno óptico (DIO).
- Cabos que possuem preenchimento por geleia de petróleo (geleado) não podem entrar mais de 15 m no prédio, devido às suas características inflamáveis.
- Caso o prédio possua diversos links de micro-ondas, satélite e outros sistemas de radioenlace, há necessidade de uma entrada especial para receber os sinais dessas antenas e levá-los até a sala de equipamentos.
- A tabela a seguir determina o espaço em parede (com 2,5 m de altura) para montagem das terminações e equipamentos de entrada numa área aberta, e na sequência a outra tabela determina as dimensões mínimas da sala para montagem das terminações de entrada e equipamentos sobre racks em local fechado.
- A decisão do uso de uma sala ou área aberta deve ser baseada nos critérios de segurança, quantidade, tipo de terminações e equipamentos, dimensões do edifício e localização dentro dele.
- Para edifícios com áreas maiores que 2.000 m², uma sala fechada é mais adequada.

![[Untitled 2 31.png|Untitled 2 31.png]]

![[Untitled 3 20.png|Untitled 3 20.png]]

Veja a figura a seguir que ilustra uma típica prancha de DG utilizada como entrada de facilidade recebendo da concessionária de telecomunicações todos os links de dados e linhas telefônicas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/6/104610/a09i05_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/6/104610/a09i05_cabestru80_100.jpg)

O EF não necessariamente deve ser instalado em uma sala exclusiva, pois essa escolha depende da quantidade de facilidades (links de comunicação e linhas telefônicas) para se determinar uma sala ou não.

Quando as facilidades não são muitas no edifício, uma caixa própria de telefonia poderá ser usada como EF – esta caixa é referenciada como "DG", que significa: distribuidor geral –, ou até mesmo uma prancha, quando se dispõe de um local seguro; e por normativa só poderá existir um DG por edificação.

**Proteção contra incêndio**

A norma EIA/TIA 569A _**obriga**_ a utilização de bloqueadores de chama em todas as aberturas existentes entre dois pavimentos.

No Brasil, dentro da área de construção civil atual, esta é uma preocupação com pouca evidência de maiores cuidados.

Técnicas de bloqueio de chamas nas aberturas destinadas à passagem de cabos entre pavimentos são muito pouco utilizadas, para prejuízo inclusive da segurança física dos ocupantes da edificação.

Como não existe uma fiscalização real desses procedimentos dentro das instalações de redes, a maioria das empresas instaladoras desconsidera a normatização colocando em risco propriedades e pessoas.