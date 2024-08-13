**Introdução**

Por definição o cabeamento horizontal é formado pelos cabos e seus caminhos, desde o Telecommunications Room até as Works Areas, incluindo o cross-connect horizontal (distribuidor secundário) alocado na sala de telecomunicações TR, e considerando todos os cabos de interligação (patch cords) e (line cords) juntamente aos pontos de consolidação ou de transição (CP ou MUTOA).

Pela Norma Brasileira NBR 54565, em sua ultima atualização de 2007, o cabeamento horizontal é chamado de cabeamento secundário, mas tem as mesmas características da normativa ANSI/TIA 568C.

**Meios físicos reconhecidos**

Os meios físicos reconhecidos para o cabeamento horizontal, segundo a normativa ANSI/TIA 568 C.1, são:

- Cabo U/UTP (Unshielded Twisted Pair) de quatro pares, 100? (ohms) categoria 5e ou superior.
- Cabo F/UTP (Foiled Unshielded Twisted Pair). Par trançado sem blindagem individual e com blindagem geral de quatro pares, 100? (ohms) categoria 5e ou superior.
- Cabo S/FTP (Screened Foiled Twisted Pair). Par trançado com dupla blindagem – individual e geral de quatro pares, 100? (ohms) categoria 5e ou superior.
- Cabo óptico multímodo de 50/125µm, incluindo os cabos otimizados para laser (OM-3).
- Cabo óptico multímodo de 62,5/125µm.

A ilustração a seguir mostra o aspecto de todos os cabos normalizados pela ANSI/TIA 568 C.1 utilizados no lançamento do cabeamento horizontal, é o tipo mais comum encontrado nos projetos e o modelo U/UTP de quatro pares.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104582/a08i01_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104582/a08i01_cabestru80_100.jpg)

**Comprimento do HC e sua topologia**

A topologia utilizada no cabeamento horizontal é a do tipo estrela, cujo centro é o rack de cabeamento, localizado na sala de telecomunicações (TR) e as pontas dessa estrela são formadas pelas tomadas de telecomunicações da área de trabalho (WA). Não são permitidas emendas e nem extensões no mesmo cabo, conforme ilustra a figura a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104583/a08i02_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104583/a08i02_cabestru80_100.jpg)

Todos esses meios devem cobrir a distância máxima de **90 metros** entre a tomada de telecomunicações e o painel de cabos (patch panel) localizado no rack de cabeamento. Para os cabos de interligação da tomada de telecomunicações aos equipamentos situados na área de trabalho utiliza-se um cabo UTP flexível conhecido como (Line Cords) de até **5 metros**, em que o tamanho-padrão de mercado é 1,80 metros e dentro das salas de telecomunicações (TR) utiliza-se outro cabo também UTP e flexível chamado de (Patch Cord) de até **5 metros**, que tem a função de interligar o painel de cabos – Patch Panel aos equipamentos ativos de rede como hubs ou switchs.

A tabela a seguir ilustra o comentado:

![[Untitled 54.png|Untitled 54.png]]

Observe que temos agora duas definições para o cabeamento horizontal lançado, dependendo da sua extensão.

Ele receberá o nome de link basic quando seu comprimento for 90 metros e será link channel se tiver 100 metros.

Quando o meio físico do cabeamento horizontal for à fibra óptica, tem-se a opção de utilizar uma topologia chamada de cabeamento centralizado.

Nessa topologia os cabos vão diretamente da tomada de telecomunicações para a sala de equipamentos, na qual haverá um cross-connect único para a fibra, e a distância máxima ficará limitada a 300m. Esse comprimento inclui os cordões ópticos e o cabeamento horizontal.

**Cross-connect horizontal**

O cross-connect horizontal é o ponto em que ocorre a interconexão ou a conexão cruzada, que permite a distribuição dos sinais de telecomunicações (voz, dados, imagem, automação etc.) nas tomadas da área de trabalho.

Os dispositivos de conexão são utilizados para terminar os cabos reconhecidos (UTP, fibra óptica) que vem da área de trabalho, em conectores reconhecidos (Conector modular de 08 vias, IDC, SC, etc.). Entre os dispositivos utilizados para a criação do cross-connect, destacam-se os patch panel nos tamanhos de 24, 48 e 96 portas e os blocos 110 de engate rápido IDC com capacidade de 50, 100 e 300 pares, conforme ilustração a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104584/a08i03_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104584/a08i03_cabestru80_100.jpg)

A normativa ANSI/TIA 568 C.1 reconhece dois tipos de conexões cruzadas, a saber:

**Conexões cruzadas (Cross-connections)**

**Interconexões (Interconnection)**

Nas conexões cruzadas, os cabos vindos das tomadas de telecomunicações e dos equipamentos ativos são ligados a dispositivos de conexão diferentes, sendo necessária a utilização de cordões de manobra (patch cord) para fazer a sua interligação.

Isso pode ser motivado pelo uso de espelhamento do ativo de rede ou para integrar equipamentos que não possuem portas baseadas em conectores reconhecidos pelas normas.

Essa maneira de conexão também é utilizada quando se necessita separar os elementos passivos (patch panel de cabos) dos equipamentos ativos (Switchs) em locais diferentes, aumentando assim, a segurança dos elementos do cabeamento estruturado, conforme ilustrado na figura a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104587/a08i04_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104587/a08i04_cabestru80_100.jpg)

Na configuração Interconexão (Interconnection), os cabos vindos das tomadas de telecomunicações instaladas nas áreas de trabalho (WA) são ligados a dispositivos de conexão (patch cords ou blocos 110) e os equipamentos ativos (switchs) podem ser ligados diretamente a estes via patch cords, conforme ilustrado a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104585/a08i05_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104585/a08i05_cabestru80_100.jpg)

**Nomenclatura das distâncias do Horizontal Cabling – HC**

Para a identificação dos trechos que formam o cabeamento horizontal, houve a divisão em duas partes, a saber:

1. Link básico ou link permanente
2. Link canal ou link channel

É o próprio cabeamento horizontal, com no máximo 90 metros de comprimento, considerando o dispositivo de conexão do cross connect horizontal (patch panel ou bloco) à tomada de telecomunicações na área de trabalho, podendo incluir um ponto de consolidação (CP) ou de transição.

O link básico ou permanente é instalado utilizando cabo FU/UTP ou F/UTP rígido, devidamente conectado nos dispositivos mencionados.

Inclui os 90 metros do cabeamento horizontal (cabo rígido), o patch cord do equipamento da área de trabalho (montado com cabo flexível), a tomada de telecomunicações, um ponto de consolidação ou de transição, se houver, e outro patch cord na sala de telecomunicações, ambos os patch cords com tamanhos não superiores a 5 metros cada, montados com cabo flexível e dois conectores RJ 45 macho conectados (crimpados) nas extremidades.

O comprimento total dos patch cords não deve ultrapassar os 10 metros, e o padrão mais utilizado para os patch cords na área de trabalho é de: 1,80 metros e na sala de telecomunicações para ativação dos pontos junto aos switchs são de 1,50 metros. A figura a seguir demonstra alguns patch cords de cores variadas para melhor identificação dos pontos, quando instalados nas salas de telecomunicações de grande densidade de pontos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104593/a08i06_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104593/a08i06_cabestru80_100.jpg)

**Sala de Telecomunicações – TR (Telecommunications Room)**

A principal função da sala de telecomunicações é a terminação do cabeamento horizontal e de backbone, abrigando os correspondentes hardwares de conectividade e equipamentos ativos de telecomunicações que forem necessários.

Além do horizontal cross-connect (HC), ela também pode conter o intermediate cross-connect (IC) ou o main cross-connect (MC). Para diferentes partes do cabeamento de backbone, proporciona também um ambiente controlado de fornecimento de energia (UPS), temperatura e umidade para abrigar os equipamentos de telecomunicações, hardware de conexão e caixas de emenda servindo a parte do prédio.

A sala de telecomunicações é um ponto estratégico dentro do sistema de cabeamento estruturado, pois é nele que é realizada a interconexão dos cabeamentos horizontal e vertical (backbone), sendo efetuado todo o gerenciamento de conexões cruzadas das tomadas com as diversas utilidades disponíveis no edifício.

No interior da sala de telecomunicações também é possível criar sistemas exclusivos e independentes das outras áreas do edifício, utilizando somente o **cabeamento horizontal** respectivo e centralização do sistema no seu interior.

Recomenda-se que haja pelo menos uma sala de telecomunicações por piso ou andar, e quando a área útil for maior que 1.000 m² ou o comprimento do cabo de distribuição horizontal até a work area for maior que 90 metros, deve-se colocar TRs adicionais. Quando existir múltiplos TRs em um único piso ou andar, recomenda-se interconectar essas salas de telecomunicações Ø3 (polegadas ou diâmetro de 75 mm) ou equivalente. Esse espaço é dimensionado em função da área útil do andar a que serve.

Na tabela a seguir temos a dimensão de alguns TR ou racks para esse fim, em virtude da densidade de pontos instalados.

![[Untitled 1 37.png|Untitled 1 37.png]]

A imagem na sequência ilustra um TR típico encontrado nas principais instalações em escritórios comerciais.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104591/a08i07_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/5/104591/a08i07_cabestru80_100.jpg)

Ao projetar uma sala de telecomunicações, algumas observações principais devem ser seguidas para que ela possa atender as suas funções, que são:

1. A altura mínima da sala deverá ser de 2,6 metros.
2. Para permitir o máximo de flexibilidade não se deve utilizar rebaixamentos de teto.
3. Para a iluminação na sala, recomenda-se 500 lux medidos a 1metro de altura do piso acabado.
4. Deve-se utilizar piso elevado com carga suportada de no mínimo de 2.400 kg.
5. Tamanho mínimo da porta deverá ser 910 mm de largura por 2.000 mm de altura e ter sua abertura voltada para fora da sala de telecomunicações (TR).

1. O sistema de controle ambiental, com pressão positiva, deverá funcionar 24 horas por dia e 365 dias por ano com os seguintes valores:  
◦  
Com ativos de rede: temperatura entre 18ºC a 24ºC e umidade relativa do ar entre 30% e 55%.  
◦  
Sem ativos de rede: temperatura entre 10ºC a 35ºC e umidade relativa do ar abaixo de 85%.  
2.  
Proteção contra incêndio.  
3.  
Deverá acessar o ponto principal de aterramento do edifício.  
4.  
Devem ser fornecidas tomadas de energia estabilizadas para os racks dos equipamentos e tomadas normais para atividades de manutenção, localizadas em intervalos de 1,8m por todo o perímetro da sala.  
5.  
Recomenda-se utilizar a codificação-padrão de cores dos dispositivos de conectividade, conforme tabela a seguir:

![[Untitled 2 30.png|Untitled 2 30.png]]