**Introdução**

Olá, bem-vindo à 20ª aula! Nela, trataremos sobre a transição do protocolo de endereços IP da versão 4 para a versão 6.

Ao contrário do que muitos acreditam, o IPv6 não é uma extensão ou complemento do IPv4, e sim um substituto, logo, não há compatibilidade direta entre os protocolos. Visto isso, foram criadas formas para efetuar a transição de IPv4 para IPv6, que discutiremos a seguir, como também há formas de fazer com que redes projetadas em IPv6 se comuniquem com redes IPv4 enquanto estas não migrem para IPv6.

Como vimos na aula anterior, o IPv4 está praticamente morto, sendo assim, todos logo migrarão para IPv6. Novos projetos de rede já devem ser realizados em IPv6 e mecanismos de IPv6 para acessar redes IPv4 devem ser considerados nesses projetos até que todos estejam em IPv6. Para antigos projetos de redes IPv4, só lhes restam migrar para IPv6, mas como isso não acontece da noite para o dia, e visto o custo e todo o investimento feito sobre IPv4, a migração não será tão rápida quanto deveria.

Existem três técnicas base de transição, são: Dual-Stack (Pilha Dupla); Translate (Tradução); Tunneling (Tunelamento). A partir dessas três técnicas, temos: 6to4, 6rd, 4rd, 6PE, 6VPE e DS-Lite, que são baseadas em Pilha Dupla; ISATAP, Túneis 6over4, Túneis GRE e Tunnel Brokers, que são baseadas em Tunelamento; TEREDO (Microsoft), NAT64, IVI, dIVI, dIVI-pd, 464XLAT, que são baseadas em Tradução. As técnicas 6to4, ISATAP e TEREDO são obsoletas; das técnicas citadas, as mais utilizadas são: Pilha Dupla, já que qualquer sistema operacional aceita o uso do IPv4 e IPv6 ao mesmo tempo, NAT64/DNS64, Túneis 6over4 e GRE.

É comum utilizar em redes locais a Pilha Dupla, em empresas de Telecom, técnicas de túneis e em provedores as técnicas de tradução; isso parece óbvio dado cada tipo de negócio.

**Técnica de pilha dupla**

Consiste em ativar tanto IPv4 quanto IPv6 em um único equipamento, dessa forma, o equipamento estará apto a se comunicar com os dois tipos de rede ou equipamentos com apenas IPv4 ou apenas IPv6.

A seguir, técnicas derivadas da pilha dupla:

- **Técnica 6to4 (RFC3056; técnica obsoleta)**: nesta técnica, utiliza-se relays de pilha dupla (abertos–públicos) distribuídos na internet, dessa maneira, quem estivesse conectado com IPv4 poderia obter conectividade em IPv6.
- **Técnica 6rd (RFC5569)**:esta é uma extensão da técnica 6to4 resolvendo os problemas de assimetria e a falta de controle sobre os relays utilizados, de modo a permitir sua utilização em larga escala.
- **Técnica 4rd**: é uma solução similar ao DS-Lite usando túneis de IPv4 sobre IPv6, mas com restrição de portas.
- **Técnicas 6PE e 6VPE (RFCs 4798 e 4659 respectivamente)**: essas técnicas permitem que redes IPv6 estabeleçam comunicação através de roteamento em MPLS com IPv4 usando LSPs (Label Switch Paths). A implementação utiliza o protocolo de roteamento MBGP (Multiprotocol BGP) sobre IPv4 para trocar rotas IPv6 desde que os roteadores de borda sejam Pilha Dupla. A diferença entre 6PE e 6VPE é que no 6PE é utilizada apenas uma tabela global, já na 6VPE são utilizadas várias tabelas separadas logicamente.
- **Técnica DS-Lite (Pilha Dupla Simplificada; RFC6333)**: essa técnica depende do provedor fornecer IPv6 nativo para os clientes e também necessita de um roteador chamado de AFTR (Address Family Transition Router), que implementa CGN (Carrier Grade NAT-NAT de Grande Porte), assim, o usuário utiliza um túnel IPv4 sobre IPv6 (Provedor) passando pelo AFTR/CGN para atingir a rede IPv4.

**Técnica de tunelamento**

Consiste em fazer com que uma rede ou host IPv6 se comunique com outra rede ou host IPv6 passando por uma rede IPv4 ou uma rede ou host IPv4 se comunique com outra rede ou host IPv4 passando por uma rede IPv6.

A seguir, as técnicas de tunelamento:

- **Técnica ISATAP (Intra-Site Automatic Tunnel Addressing Protocol; RFC5214; Obsoleto)**: esta técnica consiste em utilizar o endereço IPv4 como parte do endereço IPv6 Unicast com prefixo /64, dessa forma, os endereços IPv4 tanto do cliente quanto do roteador são usados como parte do endereço ISATAP IPv6 permitindo a um nó determinar a entrada e a saída dos túneis IPv6 sem utilizar nenhum recurso auxiliar.
- **Técnica de Túneis 6over4 (RFC4213)**: consiste em colocar um pacote IPv6 dentro de um pacote IPv4 adequando os endereços de origem e destino para o IPv4 e modificando o campo TIPO do cabeçalho para "41". Assim que o destino receber, ele remove o cabeçalho IPv4 e trata o pacote como IPv6.
- **Técnica de Túneis GRE (Generic Routing Encapsulation; RFC2784)**: essa técnica criada pela Cisco fornece um túnel estático entre dois nós, encapsulando diversos tipos de protocolos como o ISIS e o IPv6. Semelhante ao 6over4, nesta técnica são adicionados o cabeçalho GRE e o cabeçalho IPv4 ao pacote IPv6.
- **Técnica Tunnel Brokers (RFC3053)**: essa técnica permite que dispositivos isolados ou uma rede inteira IPv4 obtenha conectividade IPv6 através de um túnel fornecido por um provedor BROKER. O provedor lhe fornecerá um IPv6 dessa forma o dispositivo ou a rede trabalhará em Pilha Dupla.

**Técnica de tradução**

Consiste em modificar a comunicação de uma rede ou host IPv6 convertendo-a para IPv4 ou uma rede ou host IPv4 convertendo-a para IPv6.

A seguir, técnicas de tradução:

- **TEREDO (Microsoft; RFC4380)**: essa técnica depende de um Servidor TEREDO e um Relay TEREDO. Um dispositivo se conecta (através de UDP) ao servidor TEREDO, que efetuará o NAT; a partir daí, o dispositivo passa pelo Relay TEREDO para se comunicar com a rede IPv6.
- **Técnica NAT64 (RFC6146)**: é uma técnica STATEFUL de IPv6 para IPv4. Ele necessita de uma técnica auxiliar de DNS chamada de _DNS64 (RFC6147)_. Essa técnica é usada para que dispositivos IPv6 acessem recursos em IPv4 como WebSites, por exemplo.
- **Técnicas IVI (RFC6219), dIVI (RFC6052), dIVI-pd**: o IVI é uma técnica de tradução STATELESS 1:1 com restrição de portas, o dIVI e o dIVI-pd são extensões do IVI. No dIVI, a tradução é STATELESS 1:1 sem restrição de portas, já no dIVI-pd, pode ser designado um prefixo IPv6 em vez de um único endereço, dessa maneira, a tradução é STATELESS N:1.
- **Técnica 464XLAT**: essa técnica é similar às técnicas dIVI e dIVI-pd, usando dupla tradução de IPv4 para IPv6. Utilizando um tradutor STATELESS, chamado de CLAT (Customer Side Translator), é feita a tradução 1:1 e outro STATEFUL, chamado de PLAT (Provider Site Translator), faz tradução 1:N, em que vários IPv6 globais são representados por um IPv4 para acessar uma rede IPv4, como a internet.