**O que é virtualização?**

Virtualização é uma tecnologia baseada em software que possibilita a execução de vários sistemas operacionais e aplicativos simultaneamente em um mesmo servidor. Esta tecnologia está transformando o panorama de TI e modificando a forma não só como as empresas, mas, como as pessoas usam tecnologia. É uma a maneira eficiente de diminuir custos e despesas na área de TI, além de aumentar a eficiência e a racionalização do uso dos servidores ou computadores.

A virtualização pode aumentar a agilidade, a flexibilidade e o dimensionamento da TI e, ao mesmo tempo, permitir uma economia significativa. A implantação de cargas de trabalho é mais rápida, o desempenho e a disponibilidade são maiores e as operações se tornam automatizadas. Tudo isso resulta em uma TI mais simples de gerenciar e mais barata para ter e operar.

**Benefícios da virtualização**

·      Redução de custos operacionais e de capital;

·      Permite alta disponibilidade de aplicativo;

·      Minimiza ou elimina o tempo de inatividade.

·      Aumenta a produtividade, a eficiência, a agilidade, bem como a capacidade de resposta da TI.

·      Agiliza e simplifica o aprovisionamento de aplicativos e recursos.

·      Oferece suporte a continuidade de negócios e recuperação de desastres.

·      Possibilita também um gerenciamento centralizado.

**Tecnologia**

Virtualização é uma abstração de camada que separa o hardware físico do sistema operacional para fornecer otimização de utilização de recursos de TI e flexibilidade.

A virtualização permite múltiplas máquinas virtuais, com sistemas operacionais heterogêneos executando isoladamente, lado a lado, na mesma máquina física. Cada máquina virtual tem seu próprio hardware virtual (por exemplo: RAM, CPU, Placa de rede, etc.) em cima do qual um sistema operacional e aplicações são carregados. O sistema operacional enxerga o hardware como consistente, um conjunto de hardware em relação aos componentes físicos de hardware atual.

Máquinas virtuais são encapsuladas em arquivos, tornando fácil de serem salvas, copiadas e manipuladas. As máquinas virtuais podem ser movidas, em questão de segundos, de um servidor físico a outro para manutenção em tempo mínimo e continuamente consolida a carga de trabalho. A figura 1 apresenta a ideia de diversas máquinas virtuais rondando aplicativos em uma máquina física.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261769/14762.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261769/14762.png)

Idea da funcionalidade da máquina virtual

Fonte: tecnologiainterativa.com

Na figura 2,  tem-se um exemplo mais nítido de como ocorre a virtualização:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/9/260909/14763.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/9/260909/14763.png)

Partes de uma virtualização

Fonte: : http://www.devmedia.com.br/virtualizacao-instalacao-da-vmware-windows-server-2003/24571

Na camada externa tem-se a parte física da máquina ou Hardware que funciona com base em uma segunda camada ou sistema operacional. Para que uma máquina virtual exista, é necessário instalar sobre o sistema operacional, um software de máquina virtual ou programa de virtualização. Após, é possível criar uma nova máquina, independente das demais, cada uma com um “hardware” em particular e um espaço de armazenamento em disco, definido nas configurações da máquina virtual. Para cada maquina virtual é possível instalar um sistema operacional, podendo ser utilizado Linux, Windows ou algum outro. Pode se concluir, que na ultima camada rodam  os aplicativos, podendo ser um servidor web, e-mail, arquivos, etc.

Para que a máquina virtual aconteça, é necessário um _**hypervisor**_ **(hipervisor),** que é um software monitor de máquina virtual, ou seja, é uma plataforma que permite aplicar diversas técnicas de controle de virtualização para utilizar, ao mesmo tempo, de diferentes sistemas operativos (sem modificar ou modificá-los em caso de paravirtualização, que será explicado mais a frente) no mesmo computador. É um termo que se aplicava aos kernels dos sistemas operativos.

O hipervisores podem classificar-se em dois tipos:

·        **Hipervisor tipo 1**: Também denominado _**nativo**_, _**unhosted**_ o _**bare metal**_ (_**sobre o metal nu**_), é software que se executa diretamente sobre o hardware, para oferecer a funcionalidade descrita.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/8/260885/14766.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/8/260885/14766.png)

Hipervisor tipo 1

Fonte: http://www.devmedia.com.br/

Alguns dos hipervisores tipo 1 mais conhecidos são as seguintes: VMware ESXi (grátis), VMware ESX (Software comercial), Xen (livre), Citrix XenServer (grátis), MicrosoftHyper-V Server (grátis).

·        **Hipervisor tipo 2**: Também denominado _**hosted**_, é o software que é executado sobre um sistema operativo para oferecer a funcionalidade descrita.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/6/268675/14768.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/6/268675/14768.png)

Figura 4 - Hipervisor tipo 2

Fonte: http://www.devmedia.com.br/

O hipervisor tipo 2 mais utilizados são os seguintes: Oracle: VirtualBox (grátis), VirtualBox OSE (livre), VMware: Workstation (comercial), Server (grátis), Player (grátis), QEMU (livre), oVirt (livre), Microsoft: Virtual PC, Virtual Server.

Em outras palavras, o Hypervisor executa todo  o gerenciamento e alocação de recursos de _**hardware**_ de uma máquina virtual (VMM – Virtual Machine Monitor).  É uma camada de _**software**_ localizada entre a camada de _**hardware**_ e o sistema operacional, responsável por controlar o acesso do sistema operacional visitante (máquina virtual) aos dispositivos de _**hardware,**_ _**além de**_ prover recursos que garantam a segurança das máquinas virtuais por meio de mecanismos como isolamento, particionamento e encapsulamento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/2/261252/14769.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/2/261252/14769.png)

Ilustração do hypervisor tipo hosted e bare-metal

Fonte: http://www.devmedia.com.br/

Os servidores são frequentemente virtualizados no modo _**bare-metal,**_ _**conforme figura 5**__**.**_ Já o _**hosted**_ é comumente utilizado em soluções voltadas para uso em desktops, como o VirtualBox. A maioria dos _**hypervisors**_ oferecem recursos adicionais de _**hardware**_, que vão desde controladores USB até _**direct memory access**_ (DMA), visando com o DMA melhorar o desempenho de controladores de _**storage**_ (no que diz respeito a acesso a disco) e placas de rede.

Visto isso, a decisão de usar _**hypervisor bare-metal**_ ou _**hosted**_ vai além de “ter ou não ter sistema operacional no _**host**_”. A primeira opção, por exemplo, por estar situada diretamente sobre o _**hardware**_, conseguindo prover um número maior de opções de acesso de entrada e saída (I/O _**access**_), disponibilizando mais desempenho para aqueles que optam por essa arquitetura.

Já a segunda opção consegue prover maior compatibilidade de _**hardware**_, o que permite executar o _**software**_ de virtualização em uma gama mais ampla de configurações de _**hardware**_, diferentemente do modo _**bare-metal**_.

Como já informado, o _**hypervisor**_ utiliza os recursos oferecidos pelo sistema operacional nativo para oferecer recursos virtuais ao sistema operacional convidado que executa sobre ele.

A virtualização pode ser dividida em paravirtualização e virtualização completa.

·       **Completa:** O _**hypervisor**_ simula todo o _**hardware**_ da máquina física, fazendo com que as máquinas virtuais executem de forma isolada. Em outras palavras, o _**hypervisor**_ emula todo o _**hardware**_ para as VMs, fazendo com que o sistema operacional execute como se não estivesse em um ambiente virtual. Sua vantagem é a larga aceitação por parte de diversos tipos de sistemas operacionais.

·       **Paravirtualização**: Entrega para as VMs um _**hardware**_ igual ao real, com isso o sistema a ser virtualizado pode sofrer alterações no decorrer do tempo. Funcionalidade esta que a virtualização completa não permite, já que nela o _**hardware**_ é entregue de forma virtual. A principal característica da paravirtualização é o desempenho, ou seja, sua facilidade em se adaptar às modificações do sistema operacional devido a sua similaridade com o _**hardware**_ real.

Empregos da Virtualização

Softwares podem ser usados para gerar abstrações de recursos (reais ou virtuais) de forma que eles pareçam ser diferentes do que realmente são. Essa possibilidade é no que consiste a virtualização. Esse conceito é estendido para ser executado em três frentes: virtualização de hardware, virtualização de sistema operacional e virtualização de linguagem de programação.

Virtualização de hardware é a técnica que imita a máquina real. A máquina virtual executa em cima de um sistema operacional e outros sistemas operacionais podem ser executados em cima dela. O sistema abaixo da máquina pode ser um Monitor de Máquina Virtual ou um sistema operacional real. Exemplos de sua utilização são VMware e Xen.

Virtualização de sistema operacional é a técnica que cria a simulação de um sistema operacional, mas é implementada em cima de outro sistema. Serve para resolver, sem muitos outros ganhos significativos, a necessidade de execução de aplicações em sistemas operacionais incompatíveis. O FreeBsd Jail e o User-mode Linux representam essa categoria.

Outra forma de virtualização é a de linguagens de programação. Com ela é possível fingir que o computador se comporte diferente, ou seja, com outras instruções. A máquina virtual é responsável por executar o programa de acordo com esse comportamento fictício, do jeito que o usuário definir. Fica encarregada, portanto, de traduzir essas ações em ações do sistema operacional abaixo. Java e Smalltalk atuam nesse sentido.

O esquema da figura 6,  mostra um exemplo de cada forma de virtualização:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/2/261284/14770.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/2/261284/14770.png)

Formas de virtualização

Fonte: http://www.devmedia.com.br/

**Gestão e Automação**

Os produtos dessa categoria servem para realizar tarefas úteis no sentido de gerenciar recursos da máquina ou tornar certos processos automáticos e com melhor desempenho. Como representantes dessa linhagem podem ser citados VMWare ACE, VMWare DRS, VMWare Motion, VMWare HA e VMWare Consolidated Backup, que são disponibilizados com licenças separadas.

O VMWare ACE dá aos administradores de segurança a opção de limitar o acesso de máquinas virtuais aos recursos reais. Isso permite proteger recursos físicos. O VMWare DRS aloca os recursos levando em consideração prioridades de negócios predefinidas. O VMWare VMotion é a tecnologia que permite migrar de uma máquina virtual para outra, sem interromper os outros ambientes virtuais. O VMWare HA disponibiliza aplicativos de forma econômica.

**XEN**

O Xen é um monitor de máquina virtual (VMM ou hypervisor), em software livre, para arquiteturas x86. Originário de um projeto de pesquisa da universidade de Cambridge, sua primeira versão foi criada em 2003, 4 anos antes de ser comprada pela Citrix System, em 2007.

O Xen apresenta uma solução para virtualização um pouco diferente das apresentadas até agora. Ele consiste em criar um hypervisor, responsável por controlar os recursos das máquinas virtuais, mas que não possui drivers de dispositivos. Por isso, não é possível rodar um sistema operacional diretamente no hypervisor.

Por isso, é necessário que um sistema seja invocado para fazer a comunicação entre o hypervisor e os sistemas hóspedes. Esse sistema inicial chama-se domínio 0. Ele consiste em uma máquina virtual que executa um núcleo Linux modificado e possui privilégios para acessar dispositivos de entrada e saída e as outras máquinas virtuais.

As outras máquinas virtuais, onde podem rodar outros sistemas operacionais, são chamadas domínio U. Elas são criadas, inicializadas e desligadas através do domínio 0. Possuem um driver virtual para acesso aos recursos de hardware.

O domínio 0 possui os drivers dos dispositivos da máquina física além de dois drivers especiais que tratam as requisições de acesso à rede e ao disco enviadas pelas máquinas virtuais. Assim, toda requisição de uso da máquina real feita por uma máquina do domínio U deve ser tratada pelo domínio 0 antes de ser enviada ao hypervisor.

A figura 7, apresenta os componentes da arquitetura do Xen:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/3/261305/14771.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/3/261305/14771.png)

Arquitetura XEN

Fonte: http://www.gta.ufrj.br/grad/09_1/versao-final/virtualizacao/

Originalmente o Xen foi desenvolvido com o objetivo de implementar a técnica de para-virtualização, e, para isso, era necessário modificar os sistemas hóspedes para dar-lhes a consciência de rodarem sobre um hypervisor. Essa estratégia foi tomada visando ganhos em desempenho, mas limitou a difusão do Xen aos sistemas Unix, de código aberto.

A partir da versão 3, o Xen passou a implementar virtualização completa, podendo assim executar sistemas operacionais não modificados como Windows e Linux. Isso só foi possível após a Intel e a AMD lançarem suas arquiteturas com suporte para virtualização (Intel VT e AMD-V, respectivamente).

A fim de continuar servindo suporte a para-virtualização mas agora oferecer também virtualização completa, o Xen dividiu os domínios U entre para-virtualizados (domínios U-PV) e virtualizados (domínios U-HVM). Os domínios U-PV sabem que não tem acesso direto ao hardware e por isso precisam de drivers específicos para acesso à rede e ao disco.

Os domínios U-HVM, por não serem modificados, iniciam tentando executar a BIOS. O Xen virtual firmware é um componente que simula uma BIOS com todos os procedimentos normais de um boot. Depois, um daemon Qemu associado a uma U-HVM emula o hardware para que a máquina virtual possa usar o disco e a rede.

Virtualização em Ambientes de Redes

A virtualização é apresentada na maioria das vezes como a capacidade de fazer um mesmo hardware ser explorado por diversos ambientes computacionais. No entanto, esse conceito é mais amplo, considerando virtualização como a técnica que cria ilusões dos recursos físicos para serem explorados pelas máquinas virtuais. Nesse contexto podemos identificar essa idéia em alguns serviços implementados na Internet.

A implementação de desktops remotos, discos virtuais remotos, computação em cluster e até mesmo de dados, como XML, JMS, entre outros, apresenta o uso de recursos como se estivessem fisicamente próximos. Na verdade os recursos são explorados fisicamente em servidores potentes, longe dos usuários. Em ambientes de rede encontramos a extensão da virtualização em cima das tecnologias que permitem a troca de dados entre máquinas distantes, as redes de computadores.

Partindo dessa análise podemos dividir a virtualização em redes de computadores em duas classes: virtualização de serviços Internet e da própria infra-estrutura de rede.

Virtualização de Serviços Internet

A internet é representada através de uma abstração que define níveis que implementam serviços e se comunicam com outros níveis. Isso cria a sensação de isolamento entre as tarefas, de forma que a alteração de uma delas possa não prejudicar as demais. Isso reforça o conceito de “um servidor por serviço”, o que traz alguns incômodos.

As máquinas geram um alto custo que inclui manutenção, energia elétrica, entre outros. Gerenciar diversas máquinas também não é fácil e isso gera ainda mais custos. Além disso, projetar servidores para executarem um único tipo de serviço os torna em grande parte ociosos. A virtualização surge então para suavizar esse problema.

Como as máquinas virtuais hóspedes podem executar serviços independentes e isolados, em sistemas operacionais diferentes e na mesma máquina, o desejo de “um servidor por serviço” é mantido. Todos os serviços, porém, são empregados no mesmo hardware o que aproveita todo o poder dos servidores. Isso é chamado consolidação de servidores e gera interessantes cortes no custo do serviço

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261574/14772.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261574/14772.png)

Virtualização de serviços da Internet

Fonte: http://www.gta.ufrj.br/grad/09_1/versao-final/virtualizacao/

O modelo de virtualização que guarda dados em servidores remotos chama-se computação em nuvem. Já bastante difundido na internet, permite que dados sejam guardados em servidores remotos e que um programa rode usando esses dados. A figura 9 ilustra a computação em nuvem, já mencionado no capítulo anterior, dispersando os dados pela rede:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/8/8/278801/figura09.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/8/8/278801/figura09.jpg)

Computação em nuvem

Fonte: http://www.gta.ufrj.br/grad/09_1/versao-final/virtualizacao/

Virtualização de infraestrutura de rede

Outra utilização do conceito de virtualização consiste em criar componentes virtuais para a infraestrutura de rede. Essa técnica começa quando uma máquina virtual usa drivers para acessar a rede. Tipicamente, os drivers simulam o comportamento das camadas de rede e enlace, permitindo que as aplicações na máquina virtual enviem e recebam dados. A interface física de rede, no entanto, deve ser compartilhada entre as máquinas virtuais, o que normalmente é feito colocando-se a placa de rede em modo promíscuo e o driver de rede faz a multiplexação utilizando a técnica de token ring.

Pode-se ainda emular os próprios componentes de hardware da infra-estrutura de rede e não estão nas máquinas virtuais, como switches e roteadores. São chamados equipamentos de interconexão. Atualmente existem três formas de executar essa emulação.

VMWare, Microsoft e Citrix oferecem um produto que inclua, além da máquina virtual, suporte para uso de equipamentos de interconexão virtuais. Já a solução da Vyatta consiste em criar máquinas virtuais já com esse propósito, pois possuem uma camada de software que simula esses equipamentos. A Cisco, através da linha Catalyst, oferece um hardware projetado para suportar equipamentos de interconexão virtuais.