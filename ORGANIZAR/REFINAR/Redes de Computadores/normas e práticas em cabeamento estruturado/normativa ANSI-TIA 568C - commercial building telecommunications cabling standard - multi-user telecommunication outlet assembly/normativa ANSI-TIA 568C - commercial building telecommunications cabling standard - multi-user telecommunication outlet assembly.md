**Introdução**

Nos dias atuais, é muito comum encontrar nos ambientes de trabalhos os chamados "super escritórios", instalados em grandes andares sem paredes de alvenaria, com divisórias ou móveis modulares formando, assim, ilhas de trabalho.

Se por um lado os escritórios ficaram mais limpos visualmente, por outro lado criou-se um problema bastante sério com as constantes mudanças de _**layout**_, pois como todos usuários estão dividindo o mesmo espaço, consequentemente todos acabam sofrendo quando um serviço de reconfiguração de mobiliário faz-se necessário.

Para minimizar estes transtornos e diminuir custos com cabeamento a cada nova reconfiguração, duas técnicas foram desenvolvidas, a saber: projeto MUTOA e projeto CP.

**MUTOA -** _**Multi-user Telecommunication Outlet Assembly**_

MUTOA ou tomadas de telecomunicações multiusuários tem como objetivo principal a diminuição dos custos e a rapidez nas mudanças de um _**layout**_ dentro do espaço atendido por este projeto.

Em uma instalação convencional, os cabos UTPs partem da sala de telecomunicações (TR) do andar e são lançados até o usuário final por eletrocalhas, eletrodutos ou dutos de piso, conforme já estudado.

Esta configuração é muito parecida com uma estrela, onde temos a sala de equipamentos como centro da estrela e as áreas de trabalho como as pontas.

Na eventual mudança de _**layout**_, os cabos são lançados partindo da sala de telecomunicações, afetando, assim, usuários que muitas vezes nada tem a ver com esta mudança, visto que os cabos passam por estes usuários.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104494/a07i01_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104494/a07i01_cabestru80_100.jpg)

A técnica consiste na instalação de um ponto intermediário de distribuição, um segundo distribuidor entre a sala de telecomunicações e as áreas de trabalho. O novo ponto de distribuição poderá estar localizado próximo a um departamento, a um setor ou a usuários que tem o mesmo foco na instituição em que trabalham.

A principal vantagem deste sistema é que numa eventual mudança de _**layout**_, somente serão remanejados os cabos daquele setor a partir do distribuidor secundário, não sendo necessário remanejar todos os cabos a partir da sala de telecomunicações. A figura a seguir ilustra o comentado:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104495/a07i02_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104495/a07i02_cabestru80_100.jpg)

A _**Multi-user Telecommunication Outlet Assembly**_ (MUTOA) é uma tomada "especial", na qual múltiplos cabos horizontais terminam dentro de um escritório.

Neste caso, o cabeamento que vem da sala de telecomunicações (HC) segue direto dentro da infraestrutura até a MUTOA (o segundo distribuidor) e dela saem os cordões para a área de trabalho. Uma MUTOA pode servir no máximo 12 (doze) áreas de trabalho (WA).

A MUTOA deve ser instalada em local de fácil acesso, sobre um meio permanente, como, por exemplo, colunas e paredes estruturais. Não pode ser colocada em área obstruída, nem em mobiliário, a não ser que esteja permanentemente fixado na estrutura do prédio.

No projeto, a MUTOA permite a utilização de um _**patch cord**_ com tamanho superior a 5 metros, porém isto tem implicações diferentes, pois a utilização de lances de cabos flexíveis (_**patch cords**_) deterioram drasticamente o enlace (ponto em questão), portanto o _**patch cord**_ tem limitações de comprimento.

Esta limitação estende-se a 10 metros para o comprimento total de _**patch cords**_ no cabeamento horizontal, pois estes cabos são do tipo flexível, cuja atenuação é 20% maior do que a de cabos rígidos. Sendo assim, para não prejudicar a atenuação total do canal, foi desenvolvida uma fórmula para definir o comprimento total do _**patch cord**_, como segue:

1. Para cabos de bitola 24 AWG:C = 102 – H / 1,2 eW = C – T
2. Para cabos de bitola 26 AWG:C = 102 – H / 1,5 eW = C – T

Onde:

C = Tamanho máximo do cabo flexível permitidoH = Tamanho total do cabeamento horizontalW = Tamanho total do cabo flexível da área de trabalhoT = Tamanho total do cabo flexível da sala de telecomunicações, sendo padronizado para estes cálculos um tamanho padrão de 5 metros.

A tabela a seguir demonstra estes valores para as duas bitolas AWG normalizadas.

![[Untitled 53.png|Untitled 53.png]]

**CP -** _**Consolidation Point**_

O _**consolidation point**_, ou ponto de consolidação, é um ponto dentro do cabeamento horizontal que utiliza _**hardwares**_ de conexão de acordo com a ANSI/TIA/EIA-568-C.2. Só pode haver um ponto de consolidação no cabeamento horizontal, que deverá estar distante, no mínimo, 15 metros da sala de telecomunicações para reduzir os efeitos de NEXT (perturbações por paradiafonia) e perda de retorno. O ponto de consolidação não impede a existência de um MUTOA e deverá atender, no máximo, 12 áreas de trabalho.

O ponto de consolidação deve ser instalado em local de fácil acesso, sobre um meio permanente como, por exemplo, colunas e paredes estruturais. Não pode ser colocado em qualquer área obstruída, nem em mobiliário, a não ser que este seja permanentemente fixado na estrutura do prédio.

Diferentemente do MUTOA, onde as conexões são realizadas por tomadas fêmeas RJ 45 e macho RJ 45, no CP as conexões são feitas por meio de ferramentas e pelo uso da tecnologia IDC (_**Insulation Displacement Contact**_).

O CP deve ser instalado de modo que uma única unidade possa atender a todas as áreas de trabalho da zona, limitadas a 12 WAs. Os equipamentos terminais não podem ser conectados diretamente no CP, como o são no caso da MUTOA, mas sim por tomadas RJ 45 fêmeas, como num ponto normal de área de trabalho. Os cabos utilizados no lance horizontal são todos rígidos e são admitidos apenas cabos flexíveis no ponto da (WA) e na sala de telecomunicações.

Para as conexões dos cabos na configuração de CP são utilizados blocos de engate rápido do tipo 110 com conectores IDC, estes blocos são apresentados em três capacidades, a saber: bloco de 300 pares, bloco de 100 pares e bloco de 50 pares, distribuídos nos modelos com suportes (pernas) e sem suportes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104497/a07i04_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/4/104497/a07i04_cabestru80_100.jpg)