### Introdução

As técnicas de transição são importantes, devido ao fato de que o IPV4 e IPV6 não são diretamente compatíveis. O IPv6 não foi projetado para ser uma extensão, ou complemento, do IPv4, mas sim um substituto que resolve o problema do esgotamento de endereços. Mesmo assim, os protocolos podem funcionar simultaneamente nos mesmos equipamentos e com base nisto a transição foi pensada para ser feita de forma gradual. Para o processo de implantação do IPV6 gradativo na internet, de forma a funcionar simultaneamente ao IPV4, é chamado de “pilha dupla” ou “dual-stack”.No período de implantação do IPv6 a necessidade de técnicas auxiliares de transição se tornam interessantes, inicialmente para interconectar ilhas IPv6 em uma Internet majoritariamente IPv4 e, depois de algum tempo, para fazer o contrário.

### Técnicas de Transição

Mas como o IPV6 ainda não está sendo amplamente utilizado na internet e o esgotamento do IPV4 se tornou uma realidade, existe a necessidade de se implantar o IPv6 numa Internet sempre crescente, onde os novos usuários ainda precisam de conectividade IPv4. Existem vários cenários possíveis para a coexistência de redes IPV6 e IPV4. Pode-se classificar as técnicas de transição, segundo suas funcionalidades:

- Pilha dupla: consiste na convivência do IPv4 e do IPv6 nos mesmos equipamentos, de forma nativa, simultaneamente. Essa técnica é a técnica padrão escolhida para a transição para IPv6 na Internet e deve ser usada sempre que possível;
- Túneis: Permitem que diferentes redes IPv4 comuniquem-se através de uma rede IPv6, ou viceversa;
- Tradução: Permitem que equipamentos usando IPv6 comuniquem-se com outros que usam IPv4, por meio da conversão dos pacotes.

(SANTOS,MOREIRAS, et al., 2015)

O tunelamento baseado no GRE (Generic Routing Encapsulation) funciona praticamente da mesma forma que o 6OVER4. A principal finalidade dessa técnica é trocar pacotes entre dois dispositivos IPv6, através de uma rede IPv4. A particularidade do GRE é que ele é capaz de encapsular uma quantidade maior de protocolos e, até mesmo protocolos diferentes simultaneamente, como por exemplo o IPv6 e o ISIS. O funcionamento do GRE é simples: o mesmo obtém o pacote IPv6 a ser enviado e aplica os cabeçalhos IPv4 e GRE, que trafegam pela rede IPv4 e quando chega ao destino, os cabeçalhos são retirados obtendo-se o pacote original.

(SANTOS,MOREIRAS, et al., 2015)

![[Untitled 15.png|Untitled 15.png]]

### Pilha dupla

As Máquinas tornam-se capazes de enviar e receber, os dois protocolos, o IPv4 e o IPv6. As placas de rede, com pilha dupla, ou seja com IPv6/IPv4, ao trocar informações com uma placa de rede com  IPv6, comporta-se como um equipamento IPv6 e na comunicação com um equipamento IPv4, como uma máquina IPv4. De modo que necessita de pelo menos um endereço para cada pilha. Utilizando mecanismos IPv4, como por exemplo DHCP (Dynamic Host Configuration Protocol, responsável para atribuição automática de endereços IP, nesse caso para adquirir endereços IPv4, e mecanismos do IPv6 para endereços IPv6.

Algumas análises são exigidas:

- Configuração dos servidores de DNS;
- Configuração dos protocolos de roteamento;
- Configuração dos firewalls;
- Mudanças no gerenciamento das redes.

(SANTOS,MOREIRAS, et al., 2015)

### Tunelamento

A técnica de criação de túneis, ou tunelamento, permite transmitir pacotes IPv6 através da infraestrutura IPv4 já existente, sem a necessidade de realizar qualquer mudança nos mecanismos de roteamento, encapsulando o conteúdo do pacote IPv6 em um pacote IPv4.Essas técnicas, tratadas na RFC 4213, têm sido as mais utilizadas na fase inicial de implantação do IPv6, por serem facilmente aplicadas em teste, onde há redes não estruturadas para oferecer tráfego IPv6 nativo (SANTOS,MOREIRAS, et al., 2015).

Existem diferentes formas de encapsulamento:

- Pacotes IPv6 encasulado em pacotes IPv4: Protocolo 41, 6to4, ISATAP e Tunnel Brokers;
- Pacotes IPv6 encapsulado em pacotes GRE: Protocolo GRE;
- Pacotes IPv6 encapsulados em pacotes UDP: TEREDO.

![[Untitled 1 8.png|Untitled 1 8.png]]

Técnicas de tradução

As técnicas de tradução possibilitam um roteamento transparente na comunicação entre nós que apresentem suporte apenas a uma versão do protocolo IP, ou utilizem pilha dupla. Estes mecanismos podem atuar de diversas formas e em camadas distintas, traduzindo cabeçalhos IPv4 em cabeçalhos IPv6 e vice-versa, realizando conversões de endereços, de APIs de programação, ou atuando na troca de tráfego TCP ou UDP (SANTOS,2010).

Podem atuar de diversas formas e em camadas distintas:

- Traduzindo cabeçalhos IPv4 em cabeçalhos IPv6 e vice-versa;
- Realizando conversões de endereços;
- Conversões de APIs de programação;
- Atuando na troca de tráfego TCP ou UDP.

[https://www.youtube.com/watch?v=81PCOyxUHh4](https://www.youtube.com/watch?v=81PCOyxUHh4)

Apenas relembrando, as técnicas de transição e tunelamento são utilizadas para realizar a troca da versão do protocolo Internet Protocol (IP) que está na versão 6, essa preocupação, durante o processo de transição se deve, à complexidade e a heterogeneidade das redes de computadores, que atendem ambientes de missão crítica e que muitas vezes são importantes para o funcionamento das organizações e da economia global. Fazer a manutenção das redes de computadores, não é uma tarefa fácil, mantê-las funcionando corretamente é o trabalho dos administradores de pequenas e grandes empresas que utilizam o NOC (Network Operation Center), e a garantia de manter a rede funcional é adoção de uma estrategia criteriosa de transição, como as apresentadas nesse tópico.