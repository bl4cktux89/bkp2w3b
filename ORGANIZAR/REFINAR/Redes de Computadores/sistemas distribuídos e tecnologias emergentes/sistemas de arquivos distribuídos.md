A maioria dos Sistemas Distribuídos são organizados segundo a Arquitetura Cliente-Servidor, sendo que o **NFS** (Network File System - Sistema de Arquivo de Rede), desenvolvido pela Sun Microsystem, é um dos mais utilizados em sistemas baseados em Unix.

A ideia que fundamenta o **NFS** é que cada servidor de arquivos fornece uma visão padronizada de seu sistema local de arquivos, não importando como o sistema de arquivos é implementado, pois cada servidor NFS suporta o mesmo modelo.

O NFS vem com um protocolo de comunicação que possibilita aos clientes acessar os arquivos armazenados em um servidor, possibilitando que um conjunto heterogêneo de processos, execute em máquinas e sistemas operacionais diferentes, compartilhando o sistema de arquivos em comum.

O modelo subjacente ao NFS e a sistemas similares é o de um serviço de arquivo remoto, oferecido aos clientes por um acesso transparente gerenciado por um servidor remoto, com uma interface para um sistema de arquivos que é semelhante à oferecida por um sistema local de arquivo convencional.

Esse modelo é conhecido como **modelo de acesso remoto**, visto na figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/4/312431/20200.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/4/312431/20200.png)

Modelo de Acesso Remoto

Fonte: Figura 11.1 (a) ¿ Página 296 do Livro Sistemas Distribuídos ¿ Princípios e Paradigmas

Outro modelo oferecido é o **modelo de carga/atualização**, onde um cliente acessa um arquivo localmente, após ter descarregado do servidor, executa sua tarefa e ao término, carrega o arquivo de volta no servidor.

O serviço FTP, usado na Internet, se utiliza desse formato, quando um cliente descarrega um arquivo completo, modifica esse arquivo e o devolve.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/4/312496/20201.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/4/312496/20201.png)

Modelo de carga/atualização.

Fonte: Figura 11.1 (b) ¿ Página 296 do Livro Sistemas Distribuídos ¿ Princípios e Paradigmas

Um cliente acessa o sistema de arquivos usando uma Chamada de Sistema fornecida por seu Sistema Operacional local.

Praticamente, todos os Sistemas Operacionais modernos oferecem uma interface chamada de **VFS** (Virtual File System – Sistema de Arquivo Virtual), que substitui o sistema de arquivo do Unix, com um padrão de interface com diferentes sistemas de arquivos.

Com o sistema **NFS**, as operações na interface **VFS** são passadas para um sistema local de arquivos ou para um componente conhecido como cliente NFS, que se encarrega de manipular o acesso a arquivos armazenados em um servidor remoto. Assim, toda a comunicação cliente-servidor é realizada por meio de RPC’s (Chamada de Procedimento Remota), que é implementada no servidor através do cliente NFS.

Observe na figura abaixo, que as operações oferecidas pela interface VFS podem ser diferentes das oferecidas pelo cliente NFS, uma vez que a ideia do VFS se resume em ocultar as diferenças entre vários sistemas de arquivos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/3/3/313320/20202.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/3/3/313320/20202.png)

Arquitetura NFS básica para sistemas Unix

Fonte: Figura 11.2 ¿ Página 297 do Livro Sistemas Distribuídos ¿ Princípios e Paradigmas

No lado do servidor, vemos um NFS responsável por manipular as requisições que chegam do cliente. A RPC desmonta as requisições e o servidor NFS as converte em operações comuns de arquivo VFS que são passadas para a camada VFS, que é responsável pela implementação de um sistema de arquivos local no qual são armazenados os arquivos.

Uma vantagem do NFS é que ele é independente dos sistemas locais de arquivos e não importa se o sistema operacional do cliente implementa um sistema de arquivo Unix, Windows ou Dos, o que importa é se esses sistemas de arquivos são compatíveis com o modelo de sistema de arquivos oferecido pelo NFS.

**MODELO DE SISTEMA DE ARQUIVOS**

No modelo de sistemas de arquivos oferecido pelo NFS, os arquivos são tratados como sequências de bytes não interpretadas e são organizados hierarquicamente em um gráfico de nomeação no qual os nós representam diretórios e arquivos.

O NFS suporta ligações estritas, além de ligações simbólicas, como em qualquer sistema de arquivos Unix. Arquivos tem nome e para acessar um arquivo, um cliente deve consultar em primeiro lugar o seu nome, em um serviço de nomeação e obter o manipulador de arquivo associado.

Há vários atributos associados aos arquivos, como: o tipo do arquivo (que nos diz se é um diretório, um arquivo especial, ou outro qualquer), o comprimento do arquivo, o identificador do sistema de arquivo, entre outros.

Existem operações para ler e escrever dados em um arquivo, onde o cliente especifica o deslocamento e o número de bytes a ser lido, sendo que esse número de bytes é retornado ao cliente, com informações adicionais de status do arquivo.

Por fim, servidores NFS devem suportar dispositivos de armazenamento que possam sobreviver a falhas de fornecimento de energia, falhas de sistema operacional e falhas de hardware.

**SISTEMA DE ARQUIVOS DISTRIBUÍDOS BASEADOS EM CLUSTERS**

O NFS é um exemplo para muitos sistemas de arquivos distribuídos que são organizados de acordo com a arquitetura cliente-servidor e que muitas vezes é estendida para clusters de servidores, com algumas diferenças.

Se considerarmos que clusters de servidores são usados por aplicações paralelas, não é surpresa que seus sistemas de arquivos associados sejam ajustados de acordo com esse tipo de sistema.

Uma técnica conhecida é **desmembrar arquivos** **em tiras**, pela qual um único arquivo é distribuído por vários servidores. Assim, se distribuir um grande arquivo por vários servidores é possível buscar partes diferentes em paralelo.

É natural que tal organização só funcione bem se a aplicação for organizada de modo que o acesso paralelo aos dados tenha sentido, o que requer que os dados armazenados no arquivo tenham uma estrutura regular, como uma matriz.

Para aplicações de uso geral, ou para aquelas que tenham estruturas irregulares de dados ou muitos tipos de estruturas de dados, o desmembramento de arquivos em tiras pode não ser uma ferramenta efetiva, sendo que, muitas vezes é mais conveniente particionar o sistema de arquivos como um todo e simplesmente armazenar arquivos diferentes em servidores diferentes, mas não particionar um único arquivo por vários servidores.

Veja a diferença dessas duas abordagens na figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/6/312635/20203.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/6/312635/20203.png)

(a) Distribuição de arquivos por vários servidores e por tiras para acesso remoto. (b) Desmembramento de arquivos em tiras para acesso paralelo.

Fonte: Figura 11.3 - Página 300 do Livro Sistemas Distribuídos - Princípios e Paradigmas

**O CASO GOOGLE**

Interessante são os casos de organização de sistema de arquivos distribuídos para centrais de dados muito grandes como as usadas por empresas como Amazon e Google, que oferecem serviços a clientes Web que resultam em leituras e atualizações para uma enorme quantidade de arquivos distribuídos por dezenas de milhares de computadores.

Nesses tipos de ambientes, as premissas tradicionais referentes a sistemas de arquivos distribuídos não são válidas, pois podemos esperar que a qualquer momento um computador não funcione normalmente.

Arquivos Google tendem a ser muito grandes e contem grandes quantidades de objetos menores e, em geral são atualizados por anexação de dados a um arquivo. Essas situações, além do fato de que falhas de servidores são normais e não a exceção, é que resultou na criação, pelo Google, de seu próprio **Sistema de Arquivos Google – GFS** (Google File System) que inclui a construção de clusters de servidores.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/3/3/313323/20207.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/3/3/313323/20207.png)

Fonte: Figura 11.4 ¿ Página 300 do Livro Sistemas Distribuídos ¿ Princípios e Paradigmas

Como pode ser observado na figura acima, cada cluster GFS consiste em um único mestre com vários servidores de porção, que são divididos em porções de 64 Mbytes cada, que são distribuídas pelos denominados servidores de porção.

Outra observação importante é que um mestre de GFS é contatado apenas para obter informações de metadados, onde um cliente GFS passa ao mestre um nome de arquivo e um índice de porção, esperando um endereço de contato para a porção.

Para atender a essa finalidade, o mestre GFS mantém um espaço de nomes junto com um mapeamento de nomes de arquivo para porções.

Essa organização permite que um único mestre controle algumas centenas de servidores de porção, o que é um tamanho considerável para um único cluster.

Pela organização de um serviço como o Google em serviços menores que são mapeados para clusters, não é difícil imaginar que seja possível fazer com que um enorme grupo de clusters funcione em conjunto.

**ARQUITETURAS SIMÉTRICAS**

Existem organizações simétricas baseadas em tecnologia peer-to-peer, que usam um sistema baseado em DHT para distribuir dados, combinado com um mecanismo de consulta baseado em chaves.

O primeiro sistema de arquivos distribuídos é o **IVY**, construído com o uso de um sistema Chord baseado em DHT, que consiste em três camadas separadas, veja a figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/3/3/313337/20208.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/3/3/313337/20208.png)

Organização do sistema de arquivos distribuído IVY.

Fonte: Figura 11.5 ¿ Página 301 do Livro Sistemas Distribuídos ¿ Princípios e Paradigmas

A camada inferior é formada por um sistema Chord que fornece facilidades básicas de consulta descentralizada. No meio está uma camada de armazenamento totalmente distribuída, orientada a blocos. E na parte superior, há uma camada que implementa um sistema de arquivos semelhante ao NFS.

O armazenamento de dados no sistema IVY é realizado por um sistema de armazenamento distribuído baseado em Chord e orientado a blocos, denominado **DHash**, um sistema simples, onde a única coisa que ele conhece são blocos de dados.

O IVY usa duas espécies de blocos, um é o **Bloco de hash de conteúdo** que tem uma chave associada que é calculada como sendo o hash seguro do conteúdo do bloco. Dessa forma, sempre que um bloco for consultado, um cliente pode verificar imediatamente se foi consultado o bloco correto ou se foi retornada outra versão, ou uma versão corrompida.

O outro bloco é o **bloco de chaves públicas**, que são blocos cuja chave de consulta é uma chave pública e cujo conteúdo foi assinado com uma chave privada associada.

**PROCESSOS**

Quando se trata de processos, sistemas de arquivos distribuídos têm propriedades que não são estranhas. Em muitos casos haverá tipos diferentes de processos cooperadores, tais como: servidores de armazenamento e gerenciadores de arquivos.

Um aspecto importante referente a processos de sistemas de arquivos é se eles devem ou não ter estado. O NFS é um bom exemplo disso, pois um de seus aspectos de maior impacto, em comparação com outros sistemas de arquivos distribuídos, era o fato de que seus servidores eram sem estado.

A vantagem principal da abordagem sem estado é a simplicidade, pois quando um servidor sem estado cai, não há nenhuma necessidade de se entrar em uma fase de recuperação para trazer o servidor de volta para o estado anterior, mas é preciso levar em conta que não é possível dar ao cliente nenhuma garantia de que uma requisição foi executada ou não.

**SAIBA MAIS**

Clique no link abaixo e assista a um vídeo com um modelo de instalação de um Servidor DFS (NFS).

[**http://social.technet.microsoft.com/wiki/pt-br/contents/articles/15628.windows-server-2012-implementando-e-configurando-o-dfs-sistema-de-arquivos-distribuidos.aspx**](http://social.technet.microsoft.com/wiki/pt-br/contents/articles/15628.windows-server-2012-implementando-e-configurando-o-dfs-sistema-de-arquivos-distribuidos.aspx)

Se precisar conhecer com mais propriedade a Instalação do Sistema de Arquivos, o link abaixo apresenta um **"Guia Completo"** sobre a instalação.

[**https://technet.microsoft.com/pt-br/library/cc772778(v=ws.10).aspx**](https://technet.microsoft.com/pt-br/library/cc772778(v=ws.10).aspx)