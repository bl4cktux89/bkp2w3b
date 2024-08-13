> [!important]  
> Apresentar a disciplina, contribuindo para que o aluno compreenda os requisitos necessários para o seu cumprimento.  

### **Introdução**

Bem-vindos à aula de Gerenciamento de Redes!

Nesta disciplina abordaremos conceitos de gerência, em uma visão prática, e os aplicaremos em infraestruturas de redes computacionais, de forma simulada. Para tanto, é necessário que se tenha em mente a definição de modelo de referência OSI, a arquitetura TCP/IP, a família e a matemática do Protocolo Internet (IP), os padrões IEEE 802, infraestrutura e suas subdivisões, bem como sockets de conexão, protocolos de comunicação e roteamento. Deve-se também estar familiarizado com redes LAN/MAN/WAN.

Para que possamos aplicar os estudos serão necessárias algumas ferramentas que informaremos ao longo do curso.

Como dito antes, é importante que saibamos conceitos de rede, então, vamos relembrar alguns.

**Arquitetura TCP/IP**

Foi criada na década de 1970 com o intuito de ser um modelo simples e funcional, que permitisse a interconectividade dos "nós" (pontos ativos de rede), mesmo que um deles (ou mais, dependendo da estrutura) não estivesse ativo. É simples, porque dividiram a responsabilidade de comunicação em quatro camadas e funcional, porque estas são interdependentes, cada uma somente responde em um mesmo nível por meio de um protocolo estabelecido. Assim, deu origem às redes computacionais que usamos hoje, popularizadas na década de 1990.

**Modelo de referência OSI**

Foi criado pelo ârgão Internacional de Padronização (ISO) com o intuito de padronizar os diversos modelos existentes, uma vez que cada fabricante decidia o seu, na época, e é unanimemente aplicado às telecomunicações. Seu modelo definido a partir de sete camadas permitiu que redes Divergentes se tornassem Convergentes, de modo que a comunicação entre diferentes equipamentos e, inclusive, fabricantes fosse possível.

**Modelo internet**

Criado pela Internet Enginering Task Force (IETF), foi concebido de modo que envolvesse tanto o Modelo de Referência OSI quanto a Arquitetura TCP/IP, uma vez que a estrutura de rede mundial (das telecomunicações), que tem como base o modelo OSI, passou a trabalhar com endereços IP, integrando as tecnologias de rede existentes. A junção dos dois modelos proporciona o entendimento tanto da comunicação de curta e longa distância quanto da estrutura Cliente/Servidor de forma integrada e possibilita ganhos no âmbito do compartilhamento de informação. Assim, incorpora as três camadas inferiores do modelo OSI (Camada Física, Camada de Enlace e Camada de Rede) às duas camadas superiores da Arquitetura TCP/IP (Camada de Transporte e Camada de Aplicação). Com isso, compreendemos integralmente como um serviço de rede, desenvolvido sobre a Arquitetura TCP/IP (como DNS, web, e-mail etc.), comunica-se dentro de um ambiente cujo modelo é diferente.

**Protocolos de comunicação**

Cada camada, de quaisquer modelos, possui protocolos de comunicação específicos, mas que interagem de forma que um dado ou informação de um equipamento eletrônico possa chegar a outro e vice-versa. Essa sequência dependente das camadas chamamos de encapsulamento ou de desencapsulamento. O encapsulamento ocorre quando um equipamento quer enviar algo a outro e o desencapsulamento acontece quando um dado ou informação é recebida pelo equipamento. Imagine que você está conversando com alguém. Já parou para analisar como funciona esse processo? Resumidamente, primeiro você tem que pensar o que vai falar, depois o cérebro processa a informação e passa para a boca, mas antes de sair algum som você inspira e, ao expirar, o ar faz com que as cordas vocais vibrem, de modo que produzam uma determinada frequência. Você abre e fecha a boca, mexe a língua e então esse som é expelido pela boca; isso é encapsulamento. No processo inverso, o ouvido capta a frequência emitida, passa pelo tímpano, vai para o cérebro, que processa e interpreta e, então, a outra pessoa compreende o que você disse; esse é o desencapsulamento. Pensando no encapsulamento e desencapsulamento computacional, a cada parte do procedimento um protocolo faz um tratamento de modo a adicionar ou remover informações, fazendo isso em cada camada até que a mensagem seja colocada na rede e encaminhada ao destino ou retirada e interpretada por um aplicativo. Dessa forma, quanto menor a quantidade de camadas, menos informação é adicionada ou removida. Logo, torna-se simples a comunicação.

Com base no modelo internet, os protocolos da camada 1 (física) têm a função de codificar/decodificar os bits transmitidos e permitir seu o trânsito. Os protocolos da camada 2 (enlace) têm duas funções, a primeira de estabelecer regras de como acontecerá a comunicação entre os equipamentos (exemplo: formato Ethernet, formato PPP, formato ATM, formato Token Ring, formato Frame-Relay, formato MPLS, entre outros) e a segunda função é controlar o canal de dados. Já os protocolos da camada 3 (rede) estão divididos em dois tipos: um é responsável pelo endereçamento lógico (normalmente IP) e o outro é responsável pela comutação ou encaminhamento (roteamento) de pacotes. Os protocolos da camada 4 (transporte) têm a responsabilidade de fazer com que um dado/informação chegue ao seu destino e, finalmente, os protocolos da camada 5 (aplicação) têm a função de interpretar os aplicativos (manipulados pelos usuários) e colocar em um formato computacional, ou o contrário, transformar do formato computacional para o aplicativo, de modo que este exponha o usuário.

**Sockets**

Os sockets de conexão ou comunicação são os que nos permitem estabelecer sessões entre aplicativos ou serviços de rede. É a forma que um determinado aplicativo ou protocolo usa para ter acesso a um determinado serviço. O socket padrão da internet é usuário@HOST:Porta.

Chegamos ao final desta aula. Caso fique alguma dúvida, leve a questão ao Fórum e divida-a com seus colegas e professor.

Se necessário, procure mais informações nas referências bibliográficas. Lembre-se, apesar de um livro não ser uma luva, procure tê-lo sempre à mão.