Um proxy, inicialmente conhecido como web cache, tem função de armazenar os objetos solicitados via HTTP em uma máquina local, uma vez que podem existir novos requisições que busquem o mesmo objeto.  Este mecanismo diminui o número de acessos a WEB, melhorando o desempenho da rede, uma vez que uma quantidade menor de solicitações HTTP get irão acontecer no sentido da rede pública. É uma entidade da rede que atende requisições HTTP em nome de um servidor Web de origem. A figura 1 apresenta as requisições acontecendo em um servidor proxy (procurador) que terá a função de procurar estes objetos na WEB.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/2/257224/14268.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/2/257224/14268.jpg)

Clientes requisitando objetos por meio de um cache Web

Fonte: Kurose, James F - Redes de computadores, 2014

O proxy melhora o desempenho da rede, principalmente quando se trata de velocidade e desempenho, pois está relacionada com o tráfego e fluidez do canal para transferência de conteúdo, além de impactar diretamente na experiência do usuário no uso da rede.

Cache de conteúdos Web, Cache Web ou também Web Caching, consiste em armazenar os conteúdos das páginas Web tais como vídeos, imagens, arquivos estáticos, softwares, dados de aplicações web entre vários outros na memória ram e/ou nos discos rígidos tanto em máquinas clientes como em servidores de cache e proxy - conforme ilustrado (Figura 1), ajudando assim a diminuir significativamente o tempo médio de acesso às páginas e transferência de arquivos. Já que muitos deles são requisitados mais de uma vez, exceto no primeiro acesso, no qual o conteúdo é requisitado a um servidor externo que contêm a página ou arquivo solicitado pelo usuário.

Ao realizar processos de web cache dos conteúdos (resultantes de requisições feitas pelos usuários), outro sub-conceito necessário é a Política de Reposição (Replacement Policy), que é um algoritmo que determina qual objeto(s) deve ser despejado/removido do cache, a fim de criar espaço suficiente para adicionar um novo objeto, permitindo que outro conteúdo seja reposto no lugar. A partir deste método, aproveita-se melhor o cache dos servidores Web proxy, garantindo uma rotatividade dos objetos em disco, deixando mais ágil o processo para requisição de conteúdo. Em outras palavras, são algoritmos de expiração que o cache utiliza, a fim de eliminar documentos obsoletos, que se pode basear pelo tempo em que está armazenado, tamanho, histórico de acesso. Algumas políticas de reposição utilizadas são: Least recently used, Least frequently used, Size, GreedyDual-size e First in first out.

- Least Recently Used (LRU): menos utilizado atualmente, pois mantém no cache os objetos referenciados recentemente, e remove o objeto referenciado há mais tempo (mais antigo). O problema deste algoritmo é que ele não leva em conta o tamanho do objeto, uma vez que vários objetos pequenos podem ser substituídos por um objeto grande;
- Least Frequently Used (LFU): utilizado com menor frequência. Remove o objeto menos popular, porém não considera tempo do último acesso. Em vez disso, ele considera pelo número de acessos;
- Size: este é baseado no tamanho do objeto, substitui primeiro objetos com tamanhos maiores;
- GreedyDual-Size (GDS): atribui valores baseados no custo de um hit rate para os objetos armazenados no cache. O custo pode ser latência ou pacotes transmitidos pela rede. São mantidos em cache objeto menores, referenciados mais vezes;
- First in First out (FIFO): primeiro a entrar é o primeiro a sair, isto é, objetos são removidos na mesma ordem que entram. Não é muito usado em servidores cache.

Alguns testes verificaram que algoritmos que operam tendo como base o tamanho de objetos, beneficiam o request hit rate, enquanto que algoritmos que funcionam como base a frequência com que o conteúdo é acessado, beneficia o byte hit rate.

O objetivo principal de um servidor proxy é possibilitar que máquinas de uma rede privada possam acessar uma rede pública, como a Internet, sem que para isto tenham uma ligação direta com esta. O servidor proxy costuma ser instalado em uma máquina que tenha acesso direto à Internet, sendo que as demais efetuam as solicitações através desta. Justamente por isto este tipo é chamado de proxy, pois é um procurador, ou seja, sistema que faz solicitações em nome de outros.

O proxy/cache colabora com três dos maiores desafios dos clientes, sendo eles:

- Aceleração de aplicações e conteúdo Web: o proxy/cache reduz a latência, utilização de banda e sobrecarga nos servidores, aumentando a distribuição do conteúdo Web e aplicações baseadas em Web como sistemas de CRM (Customer Relationship Management) e ERP (Enterprise Resource Planning);
- Segurança na Internet: pode-se implementar processos de segurança, incluindo proxy, caching, controle de acesso, filtragem de conteúdo, anti-virus web, scanning SSL (Secure Sockets Layer), bloqueio de Instant message (msn messenger, AOL Instant Messenger) e P2P (peer to peer conection), antispam e relatórios;
- Distribuição de vídeo: O proxy/cache melhora a qualidade dos treinamentos online, vídeos executivos e serviços de vídeo sob demanda.

### **Modelos de proxy**

O proxy possui diversas formas de implementação e operação, cada um possui características e objetivos específicos que melhor atendem aos requisitos dos clientes para um determinado do tipo de rede, empresas ou instituições de ensino, sendo eles: Web proxy: Também denominado de Web proxy/cache, é o tipo mais comum de proxy existente, realiza o caching de páginas web e arquivos que estão localizadas nos servidores Web externos, possibilitando que os usuários da rede local (LAN) tenham um acesso mais rápido e confiável aos conteúdos da Internet - por eles requisitados, através do armazenamento em cache dos recursos Web, tais como conteúdos estáticos como figuras e gráficos

**Proxy reverso:**

Como o próprio nome diz, o proxy reverso funciona ao contrário do proxy. No modelo convencional de proxy se faz a interceptação das requisições dos clientes que estão localizados na rede local (LAN) com destino à Internet. Enquanto que no proxy reverso a operação é inversa, interceptando requisições vindas da Internet com destino à rede local. Em suma, ambos são responsáveis em garantir que o cliente não tenha uma conexão direta com o servidor que armazena o conteúdo requisitado, a fim de garantir o anonimato das estações clientes.

Os benefícios de utilizar proxy reverso os seguintes aspectos:

- Segurança: como o proxy é a única interface externa da rede, ele ?esconde? os demais servidores;
- Criptografia: a criptografia SSL pode ser delegada ao proxy ao invés dos servidores internos;
- Balanceamento de carga: o servidor pode distribuir a carga para vários servidores da rede;
- Cache: assim como o web proxy, o proxy reverso pode manter em cache o conteúdo estático das requisições realizadas, ajudando assim a diminuir a carga dos servidores web; e,
- Compressão: o proxy reverso pode tornar o acesso mais rápido através da compressão do conteúdo acessado.

**Proxy transparente:**

Conhecido também como transproxy, é o tipo de proxy onde não é necessário fazer configurações adicionais nas estações clientes (nos navegadores dos computadores, por exemplo), visto que ele combina NAT (Net Address Translation) com o servidor proxy, facilitando assim o uso dele em instituições de ensino e empresas, reforçando as políticas de uso da rede. Em casos onde não se utiliza este método, numa configuração manual, por exemplo, há então a necessidade de especificar manualmente nos navegadores o endereço IP (Internet Protocol) do proxy bem como a porta de operação. Como benefícios de sua utilização, destaca-se o protocolo de roteamento de conteúdo Web Cache Communication Protocol (WCCP), ver aula 5, desenvolvido pela Cisco Systems em 1997; criado com mecanismos de balanceamento de carga, redundância, tolerância a falhas e garantia de serviço (failsafe). Presente nos roteadores Cisco, ele permite redirecionar o fluxo de tráfego de rede em tempo real. Quando se utiliza roteadores com o protoloco WCCP implementado junto com o servidor proxy transparente, eles permitem atuar como intermediário entre a rede local e a internet, provendo uma distribuição inteligente de caches de rede para maximizar o desempenho de download e disponibilidade de conteúdo, reduzindo e otimizando assim a utilização do link de Internet.