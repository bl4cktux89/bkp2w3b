Matrizes de tráfego (MT) refletem o volume de tráfego que flui entre todos os possíveis pares origem e destino na rede. A aquisição de dados medidos para preencher uma matriz de tráfego apresenta alto custo de coleta e computacional (Medina; 2002).

Isto torna necessário o uso de técnicas de estimação baseadas em informações parciais. A estimação de matrizes de tráfego é fundamental para muitas questões da engenharia de tráfego, auxiliando no planejamento do crescimento de redes e diagnósticos de problemas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/9/269998/13099.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/9/269998/13099.jpg)

Internet

### Internet hoje

A estrutura e a composição da Internet se adaptaram conforme as necessidades mundiais também mudavam.  A Internet de hoje serve o maior e a mais diversificada comunidade de usuários de rede no mundo.

Os backbones  contemporâneos  da Internet,  hoje  são  uma coleção de provedores de serviços que têm pontos de conexão chamados POPs (_**point of presence**_) em várias regiões.

Um conjunto de POPs e a infraestrutura que os interconecta formam a rede de um provedor. (Ex. Vivo, Claro, TIM, NET, etc).  Os clientes estão conectados a seus provedores via acesso ou instalações de hospedagem no POP de um provedor de serviços.  Esses clientes também  podem ser próprios provedores de serviços na internet.

Para permitir que os clientes de um provedor troquem dados com  clientes conectados a outro provedor, o tráfego é trocado em Networks Access Points  (NAPs), também conhecidos como pontos de troca de tráfego (PTT) ou através de interconexões diretas.

O termo ISP (_**Internet servisse provider**_), provedor de serviços de Internet,  é comumente usado para se referir a qualquer pessoa que fornece serviço de conectividade à Internet, seja diretamente ao usuário final, ou a outros provedores de serviços. O termo NSP (Network Service Provider) era tradicionalmente usado para se referir a provedores de rede backbone. No entanto, NSP agora é usado muito mais vagamente para se referir a qualquer prestador de serviços que tem uma presença nos NAPs e mantém uma rede backbone, sendo assim em muitas vezes o termo INSP (Internet Network Service Provider) com a conotação do proprio NAP.

### Funções de um NAP ou INSP

- Manter o NAP/INSP com conexão a backbones de altas velocidades permitindo a troca de trafego com outras redes (ISP).
- Estabelecer políticas e taxas para os provedores de serviços que desejam se conectar ao NAP/INSP.
- Propor os locais NAP/INSP sujeitos a determinadas localizações geográficas.
- Propor e estabelecer procedimentos para trabalhar com outros NAP/INSPs, resolvendo problemas de troca de trafego e apoiar a qualidade de serviço de ponta a ponta (QoS) para usuários de rede.
- Desenvolver padrões de confiabilidade e segurança para os NAP/INSPs, bem como procedimentos de acompanhamento para assegurar o cumprimento das normas.
- Especificar e fornecer relatórios estatísticos de uso.
- Especificar os procedimentos de acesso físico apropriados às instalações do NAP/INSP para pessoal de redes e assegurar que estes procedimentos sejam realizados.

### Configurações físicas de um NAP ou INSP

A configuração física do NAP atual é uma combinação de switches FDDI, ATM e Ethernet (Ethernet, Fast Ethernet e Gigabit Ethernet).  Normalmente, o provedor de serviços gerencia roteadores colocados em instalações NAP. O gerenciador NAP define configurações, políticas e taxas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/7/0/327021/21897.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/7/0/327021/21897.png)

Exemplos de Backbone

### ISP Serviços e Características

Qualquer pessoa que pode oferecer conectividade com a Internet poderia reivindicar ser um provedor de serviços.  O termo "provedor de serviços" abrange tudo, desde um provedor com uma estrutura multimilionária e uma infraestrutura até um provedor com um único roteador e servidor de acesso em sua garagem.

O valor não deveria  ser o principal fator para decisão de escolher um ISP. Os pontos principais são fatores como os serviços do provedor, design backbone, tolerância a falhas, redundância, estabilidade, gargalos, provedor / equipamentos  de clientes, e assim por diante.

Os comportamentos de roteamento na Internet são afetados pelo modo como os protocolos de roteamento e o tráfego de dados se comportam em uma infraestrutura física que utilizam matrizes de tráfego para o encaminhamento entre  os vários ISPs. O bom projeto e manutenção de infraestrutura são fatores primordiais na obtenção de roteamento saudável na Internet.

**Tipos de tecnologias de acesso aos ISP.**

- Linhas discadas
- Links Frame-Relay ou ATM
- Acessos dedicados
- Fibras óticas
- Cable Modems
- DSL (Digital Subscriber Line)
    - ADSL
    - HDSL
    - SDSL
    - VDSL
- Redes hibridadas GPON
- Acessos 3G/4G
- WiMax
- Radios dedicados

O vídeo abaixo traz uma apresentação sucinta mas essencial para o entendimento do conceito de “troca de tráfego” e dos “pontos de troca de tráfego”, realmente o que faz a Internet funcionar!

[**https://www.youtube.com/watch?v=hswxxB5MpY8**](https://www.youtube.com/watch?v=hswxxB5MpY8)

### Design de rede - Network Design

O design de rede consiste em três partes ou subproblemas: **posicionamento de nó, colocação de links e atribuição de capacidade (para nós e links).**

O subproblema de posicionamento do nó trata da colocação geográfica dos nós da topologia que entre os POPs  e o  INSP. O subproblema de colocação de links trata da conexão dos nós entre si, mas o problema de atribuição de capacidade atribui capacidades (largura de banda, buffer, etc.) aos nós e links. Para projetar uma topologia completamente nova, todos os três desses subproblemas precisam ser resolvidos (Heckmann, 2006).

Há uma quantidade de trabalhos relativos à concepção da rede. Han et al. (2000) apresentam uma abordagem com a função de custo bem mais realista para os links. Essa função é a sequência de passos de como abordar a questão de custo de capacidade, ou seja, o problema de otimização de interconexão. Vários pesquisadores mostram que o problema de otimização pode ser reformulado em um problema de otimização mais simples onde cada link é substituído por vários links com custos constantes e um limite de capacidade. (BERRY, 1998; RANDALL, 2000; GLOVER, 1998; KERSHENBAUM, 1993).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/5/6/355677/29778.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/5/6/355677/29778.jpg)

Network Design

Fonte: The Competitive Internet Service Provider: Network Architecture, Interconnection, Traffic Engineering and Network Design Oliver Heckmann 2006 John Wiley & Sons, Ltd

### Engenharia de redes - Network Engineering

Contrariamente aos problemas de projeto de rede que são sobre a síntese de uma nova topologia, engenharia de rede trata sobre a melhoria de uma topologia de rede existente, quer está devasada por congestionamento de nós e / ou links (engenharia estrutural) ou pela necessidade de expansão da capacidade de uma rede existente. Redes novas têm que ser projetadas raramente porque praticamente todos os INSPs já têm redes existentes. Portanto, a engenharia de rede é um desafio mais frequente e importante para os INSPs (Heckmann, 2006). Os volumes de tráfego estão crescendo 70-150% ao ano, segundo Odlyzko (2003).

A largura de banda de uma rede tem que ser dobrada aproximadamente a cada ano para manter o ritmo com essas taxas. Isso leva à conclusão de que a expansão da capacidade - especialmente a expansão da capacidade de ligação - é o mais importante de todos os desafios de engenharia de rede. Por exemplo Hasslinger e Schnitter (2004) investigam a expansão da capacidade de ligação e a engenharia de tráfego para redes IP. Com base na sua experiência com o backbone IP para a empresa alemã Telekom, eles relatam fatores de aumento de capacidade que vão além de um fator de 2 por ano!

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/5/6/355679/29779.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/5/6/355679/29779.jpg)

Network Engineering

Fonte: The Competitive Internet Service Provider: Network Architecture, Interconnection, Traffic Engineering and Network Design Oliver Heckmann 2006 John Wiley & Sons, Ltd

**TRAFFIC ENGINEERING**

O IETF dá a seguinte definição de engenharia de tráfego: A engenharia de tráfego da Internet é o estudo da engenharia de rede, envolvida com a otimização de desempenho de tráfego em redes operacionais, com minimização e otimização sobre a utilização de recurso entre outras redes com capacidade disponível.

### Engenharia de Tráfego - Traffic Engineering

A engenharia de tráfego trata basicamente com problemas de optimização, sendo assim os INSPs terão rede com capacidade hora suficiente e hora não. A engenharia de tráfego usa uma matriz de tráfego como entrada para determinar os encaminhamentos. Em alguns casos, a matriz de tráfego pode ser conhecida exatamente e antecipadamente, mas normalmente a matriz de tráfego não é conhecida tendo que ser estimada com base em medições (Heckmann, 2006). A estimação da matriz de tráfego é um desafio para os INSPs, Roughan et aL. (2003) faz uma pergunta importante: **Se a engenharia de tráfego é feita com base na matriz de tráfego estimada, como é o funcionamento na matriz de tráfego real?**

As matrizes de tráfego formam a entrada para problemas de otimização de engenharia de tráfego e design de rede. Portanto, é importante determinar matrizes de tráfego em redes reais. Abordagens a este problema podem ser classificadas em **métodos topográficos estatísticos, métodos topográficos baseados em otimização e outros métodos**:

- O método estatístico usa modelos estatísticas da ordem superior da carga de dados dos links como a escoamento entre duas cargas para criar restrições adicionais (CAO, 2000; TEBALDI, 1998; VARDI, 1996).
- Os métodos baseados na otimização selecionam algumas soluções dentro das melhores e otimizam uma determinada função objetivo usando métodos como programação linear ou quadrática. Os trabalhos do pesquisador Goldschmidt (2000), é exemplo dessa abordagem.
- Classificados como outros métodos são abordagens que combinam os métodos estatísticos e baseados em otimização com outros métodos que utilizam algoritmos baseados em heurísticas como gravidade ou modelos de escolha, exemplo do trabalho apresentado por Medina et al. (2002), por fim o processo de decisão é modelado como um problema de maximização.

### Métricas de desempenho de engenharia de tráfego

Para a avaliação da engenharia de tráfego, existem várias maneiras de utilizar as matrizes de tráfego, modificando as métricas para encaminhados. As métricas que podem ser usadas para avaliar o desempenho do roteamento são mostradas abaixo (Heckmann, 2006):

- Comprimento do percurso
- Utilização máxima de gargalos
- Utilização média
- Carga Média
- Custos de Congestionamento