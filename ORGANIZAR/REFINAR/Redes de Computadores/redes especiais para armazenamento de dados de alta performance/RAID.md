### Introdução

Em um ambiente de _**Data Center**_ onde temos serviços e informações extremamente importantes para as organizações é altamente recomendável que o ambiente possua um Plano de Recuperação de Desastres (DRP – _**Disaster Recovery Plan)**_ de modo a garantir a continuidade dos negócios.

Umas das técnicas capazes de replicar e manter os dados redundantes é o RAID, que é capaz de combinar vários drives de discos rígidos (HD-_**Hard Disks**_) em uma unidade lógica. RAID significa (_**Redundant Array of Independent Disks**_ ou conjunto redundante de discos independentes), as principais funções desse recurso é gerar redundância ou paridade, otimizar o processamento.

Em um plano de DRP é comum adotar técnicas como o RAID; por isso usa-se da replicação de dados como um artefato para manter os serviços sempre disponíveis, uma vez que algum dispositivo ou sistema apresente problemas. O objetivo é criar algo que seja sólido, que os usuários não percebam quando houver falhas, e não perder dados e informações.

Nesse tópico serão apresentadas as várias formas de implementação, técnicas e níveis mais comuns de uso de RAID.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/8/1/0/7/2810744/-comp-final.gif)](https://img.uninove.br/static/0/0/0/0/0/0/2/8/1/0/7/2810744/-comp-final.gif)

Fonte: https://animagraffs.com/hard-disk-drive/

### Definição de RAID

Em 1987, Patterson, Gibeson, e Katz da Universidade da California, Berkeley, publicaram um artigo intitulado " _**A Case for Redundante Arrays of Inexpensive Disks**_ (RAID)". Este artigo descreve o uso de pequena capacidade, disk drives baratos como alternativa para suportar largas capacidades de armazenamento comuns em computadores do tipo main-frames. O termo RAID tem sido redefinido para se referir a discos independentes que reflitam avanços na tecnologia de armazenamento. A tecnologia RAID cresceu de um conceito acadêmico para um padrão na industria e é comumente empregada nas áreas de armazenamento em disco.

RAID é a técnica de combinar múltiplos disk drives em uma unidade lógica (RAID Set) e ainda promover proteção, performance, ou os dois.

Devido aos componentes mecânicos, o disk drive oferece performance limitada.

Uma unidade de disco oferece uma certa expectativa de vida que é medida em MTBF, (Mean time between Failure, ou Tempo médio entre falhas, que pode apresentar uma média de vida útil do componente). Por exemplo, se o MTBF de um drive é 750.000 horas e existe 1000 drives na tabela, então o MTBF da tabela de discos é de 750.000 / 1000, ou seja, 750 horas.

RAID foi introduzido para mitigar este problema.

Hoje em dia os data centers abrigam centenas de disk drives em sua infraestrutura de armazenamento. De acordo com a Dell Corporation (2015) Drives de Discos são susceptíveis a falhas devido ao seu mecanismo interno e também a fatores do ambiente onde se encontram, o que resulta em perda de dados. Quanto maior o número de disk drivers numa área de armazenamento de dados, maior a probabilidade de falha nesta área. Por exemplo, considere uma área de armazenamento contendo 100 disk drivers, cada um tendo uma expectativa de vida de 750.000 horas de funcionamento. A expectativa de vida média para esta área é de 750.000 / 100, ou seja, 7. 500 horas. Isto significa que um disk drive irá falhar a cada 7.500 horas.

RAID é uma técnica que permite alavancar vários múltiplos drives como parte de um conjunto que provê proteção do dado contra falhas do drive. Em geral, a utilização de RAID também aumenta a performance do sistema de armazenamento, economizando I/Os de múltiplos discos simultaneamente.

**RAID - INTRODUÇÃO AO CONCEITO DE RAID**

Vídeo publicado por **Dell Suporte Brasil**

Disponível em: <[**www.youtube.com/watch?v=PMX61TisJgY**](http://www.youtube.com/watch?v=PMX61TisJgY)>. Acesso em 17/08/2018

### Componentes do Array RAID.

Um _**array**_ do RAID é um compartimento com um número de drives de discos que ajudam o _**hardware**_ a implementar o RAID. Um subconjunto de discos dentro do _**array**_ do RAID pode ser agrupado para formar associações lógicas, chamadas de _**arrays**_ lógicos também conhecidos como conjunto RAID ou grupo RAID.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267701/12026.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267701/12026.png)

Componentes do Array RAID

### Métodos de Implementação RAID.

Existem dois métodos de implementação do RAID. Ambos têm seus pontos fortes e fracos. RAID em software utiliza o software do host para prover as funcionalidades RAID e é implementado ao nível do sistema operacional.

A implementação de **RAID em software** oferece benefícios em termos de custo quando comparado com RAID em hardware, porém percebe-se as seguintes limitações:

- Performance: RAID em software afeta a performance do sistema como um todo e ainda requisita ciclos de CPU para cálculo do RAID.
- Funcionalidades suportadas: RAID em software não suporta todos os níveis de RAID.
- Compatibilidade com o sistema operacional: RAID em software é uma fatia do sistema operacional, portanto upgrades para o software RAID ou sistema operacional tem que ser valido para ambos.

Na implementação de **RAID em hardware**, um hardware de controle especializado é implementado tanto no host quanto no array. Esta implementação varia de acordo com as interações do array com o host. Controller card RAID é baseado no hardware do RAID e para o qual um controlador especial também é instalado nos drivers de disco com os quais está conectado. Os fabricantes também integram controles no "motherboards", porém o RAID baseado em host não é uma solução muito eficiente no caso de ambientes de data center com um grande número de hosts.

O controle externo de RAID é um hardware baseado no array do RAID e age como uma interface entre o host e os discos. Ele representa um volume de _**storage**_ para o _**host**_ e o host administra estes volumes como se fossem discos físicos. As funções chave do controlador RAIS são:

- Administrar e controlar agregações de discos.
- Transcrever as requisições de I/O entre discos lógicos e físicos.
- Regeneração de dados em uma eventual falha do disco.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267703/12034.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267703/12034.png)

Métodos de Implementação RAID.

### Técnicas RAID

Bem, já entendemos que RAID serve para agrupar Drives em um conjunto, porém temos algumas técnicas para fazer isso.

- _**Striping**_ Fracionamento
- _**Mirroring**_ - Espelhamento
- _**Parity**_ - Paridade

Técnica de FRACIONAMENTO: que consiste em dividir a mesma informação em vários discos, porém isso não oferece nenhuma segurança.

Técnica de ESPELHAMENTO: Cria uma cópia exata do disco A no disco B.

Técnica de PARIDADE: salvar no disco C a diferença entre o disco A e B, dessa forma, caso tenha alguma perda de dados, eles podem ser recuperados matematicamente.

Também temos combinações dessas técnicas, que podem ser chamados de níveis de RAID.

Abaixo os níveis de RAID mais comuns:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267910/12008.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267910/12008.png)

Níveis de RAID.

**RAID - CONHECENDO OS NÍVEIS DE RAID**

Vídeo publicado por **Dell Suporte Brasil**

Disponível em: <[**www.youtube.com/watch?v=8V5FoTQpjIE**](http://www.youtube.com/watch?v=8V5FoTQpjIE)>. Acesso em 17/08/2018

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267921/11990.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267921/11990.png)

Níveis do RAID adequado para diferentes aplicativos.

Sempre que for escolher qual RAID usar, sempre tome cuidado com o desempenho, imagine o seguinte, uma RAID 0, que só fraciona um dado e o grava, será bem mais rápido do que um RAID 6, que fraciona, mas cria duas paridades. O tempo de gravação será bem maior! Porém a segurança e garantia de integridade de dados é maior também. Sempre avaliem todos os aspectos!

### _Hot Sparing_

_**Hot sparing**_ é a técnica de substituir temporariamente um disco com problemas, o que acontece basicamente é a como seu pneu fura, você para o carro, pega o estepe, e troca para continuar sua viagem, porém na parada mais próxima você arruma o pneu o mais rápido possível. Similar ao pneu, se um disco assume o papel de outro, e acontecer outra falha, você perderá dados. Essa troca pode ser automaticamente ou feita manualmente pelo administrador.

### Acessando os dados

Os dados são acessados por meio de protocolos pré-definidos, como o SCSI, FC(Fiber Channel), IDE e ATA, onde basicamente, a controladora solicita alguma operação de E/S ou I/O ( Entrada e Saida / _**Input e Output**_) para o sistema de arquivos por meio de um protocolo.Dessa forma, o que vai diferir as maneiras de acessos principalmente é o tipo de sistema de armazenamento que estamos usando, temos sistemas baseados em arquivos, block, objetos e unificados. No block os sistema de arquivo é montado pelo sistema, e as informações acessadas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267908/12007.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267908/12007.png)

RAID 0.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/8/267898/12005.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/8/267898/12005.png)

Raid 1

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/8/267897/12003.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/8/267897/12003.png)

Raid 1+0

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/0/6/8/2906865/42532.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/0/6/8/2906865/42532.png)

Fonte: Internet e Redes sociais

### RAID Technique - Mirroring.

_**Mirroring**_ ou espelhamento é uma técnica na qual dados são armazenados em dois drive de discos diferentes, produzindo duas cópias do dado. No caso de uma falha no disco, o dado continua intacto na cópia do disco que não sofreu falha e o controlador continua servindo as requisições de dados do host a partir do disco intacto devido ao espelhamento do par.

Quando o disco for recuperado ou trocado por outro, o controlador copia o dado a partir do disco que não falhou para seu par espelhado. Esta atividade é transparente para o host.

Para providenciar uma completa redundância o espelhamento habilita uma rápida recuperação de falha de disco. Entretanto espelhamento de disco provê apenas proteção de dados e não é substituto de backup de dados. O espelhamento captura constantemente as mudanças do dado, enquanto que o backup captura imagens de dados  em um ponto no tempo

O espelhamento envolve a duplicação do dado - a capacidade total de armazenamento é duas vezes o total de dados a ser armazenado. O espelhamento é considerado um recurso caro e portanto é utilizado para aplicações de missão crítica que não pode perder dados. O espelhamento permite boa performance de leitura porque as solicitações podem ser servidas por qualquer um dos dois discos. Entretanto a performance de gravação é mais lenta em comparação com aquela feita em um único disco, porque cada solicitação de gravação manifesta duas gravações físicas em discos diferentes. Em outras palavras, o espelhamento não apresenta a mesma performance de gravação quando comparado ao striped RAID.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/8/267891/12001.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/8/267891/12001.png)

RAID 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257190/14468.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257190/14468.jpg)

RAID 4

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257191/14466.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257191/14466.jpg)

RAID 5

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/8/267882/11993.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/8/267882/11993.png)

RAID 6.

Em nível de arquivo, os dados são separados hierarquicamente, geralmente em um servidor separado, e ele gera mais sobrecarga do que o armazenamento block.

E por último, a nível de objeto, que é armazenar o dado e seus metadados (informações sobre esse dado) para o encontrar mais facilmente.

A necessidade de organização dos dados digitais, assim como a alta disponibilidade nos principais ativos que suportam o negócio da empresa fez com que os responsáveis pela infraestrutura de servidores implementassem soluções que aumentassem o grau de proteção dos seus servidores.

Essas medidas partiram desde a duplicação de componentes dos servidores, bem como a duplicação de dispositivos que ajudavam esse servidor a ficar ligado.

Dentre os componentes que ajudam a manter a alta disponibilidade dos servidores existe um que é responsável pela segurança dos discos (HD) desses servidores.

A ideia seria colocar uma proteção para esses discos, de forma que se houvesse uma falha, os equipamentos continuariam funcionando mesmo que parcialmente, até o momento que pudesse ser feita a troca do dispositivo.

Antes de abordar esse tema, faz-se necessário o entendimento de alguns itens relacionados a seguir:

- Disco SCSI (_**Small Computer System Interface**_) – trata-se de uma tecnologia criada para acelerar a taxa de transferência de dados e utilizadas em discos que suportam HDC. O HDC possibilita conectar e desconectar discos rígidos sem a necessidade do desligamento da máquina.
- HDC – (_**Hot Desconnect and Connect**_ ou Conectar e desconectar HDs a quente).
- _**Hot Spare**_ – está relacionado ao fato de um dispositivo estar pronto para ser usado para que seja feito o processo de reconstrução de um disco quando ele apresenta uma falha.
- _**Rebuild**_ – esse termo está associado à palavra reconstrução. Geralmente quando um disco falha e o processo de reconstrução é iniciado, o termo _**Rebuild**_ refere-se aos discos que são utilizados.
- _**Array**_ – agrupamento ou conjunto de disco.
- O RAID (_**Redundant Array of Independent Disks**_) – matriz ou conjunto redundante de discos independentes.

### Resumo

Resumidamente podemos definir o RAID, como sendo um sistema formado por um conjunto de discos (HD) independentes que trabalharão juntos (formando uma única unidade lógica) para deixar um equipamento com melhores critérios de tolerância a falhas "Redundantes". Essa tecnologia foi desenvolvida para aumentar o desempenho de acesso e a confiabilidade dos dados em um servidor. O sistema de RAID possibilita que o responsável pela segurança dos servidores possa escolher qual tipo implementar, de acordo com a necessidade de capacidade, desempenho, confiabilidade que o seu cenário de proteção necessitar de acordo com as várias formas de implementação, técnicas e níveis mais comuns de uso de RAID. Neste tópico também foi descrito os métodos de Implementação RAID, as técnicas RAID: _**Mirroring Striping e Parity**_, além da forma de recuperação de dados na Técnica de Paridade. Discutimos também os níveis de RAID que são: RAID 0, RAID 1, RAID 1 + 0, RAID 3, RAID 5 e RAID 6, além da abordagem sobre o impacto em performance causado pelo uso de RAID.