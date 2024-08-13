**Introdução**

Sabemos que o endereçamento IPv4 tem suas limitações e, inclusive, para a maioria dos países, incluindo o Brasil, não há mais endereços IPv4 públicos (roteáveis na Internet) disponíveis. Por essas e outras razões foi criado o padrão IPv6.

Veja esse breve vídeo, produzido pela equipe do NIC.BR, para entender melhor esse contexto:

**O que é o IPv6, em português claro**: [**https://www.youtube.com/watch?v=_JbLr_C-HLk**](https://www.youtube.com/watch?v=_JbLr_C-HLk)

Um outro motivo muito importante da implantação do IPv6, é o advento da Internet das Coisas (ou IoT – _**Internet of Things**_, em inglês).

Essencialmente, IoT significa que praticamente tudo que utilizamos, como geladeiras, sistemas de iluminação, babás eletrônicas ? estamos falando de aparelhos, não de um robô ? dentre outros dispositivos, terá um endereço IP e estará conectado a uma rede interna ou, em muitos casos, à própria Internet.

Isso significa que o suporte a um número gigantesco de endereços roteáveis será crucial.

Nesse tópico, apresentaremos as principais mudanças implementadas pelo IPv6, em termos de cabeçalho (_**header**_).

**Cabeçalho base do IPv6**

O IPv6 não apenas possibilitou a utilização de um número bem maior de endereços roteáveis na Internet, mas implementou várias melhorias em relação ao padrão IPv4, a começar pelo próprio cabeçalho, ou estrutura, do mesmo, que ficou muito mais simples. A Figura 1, abaixo, mostra as diferenças entre o cabeçalho IPv4 (em cima) e o cabeçalho IPv6 (em baixo):

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/5/4/9/7/1549779/37266.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/5/4/9/7/1549779/37266.png)

Figura 1 - Cabeçalhos IPv4 e IPv6.

Podemos destacar como fatores que contribuíram para essa melhoria, em termos de simplicidade, a quantidade de campos, que diminui para apenas oito e o tamanho do próprio cabeçalho que, enquanto no IPv4 era variável, no IPv6 foi fixado em 40 bytes (lembrando que 1 byte é um conjunto de 8 bits que, por sua vez, é a menor medida de uma informação, em termos computacionais).

A remoção de vários campos do IPv4 foi possível devido a própria **inutilidade de alguns deles no contexto atual** como, por exemplo, o _**checksum**_ ? uma vez que as camadas superiores possuem seus próprios mecanismos de validação da integridade da informação, e da **especificidade** de outros, que passaram a integrar o que se chama no IPv6 de **cabeçalhos de extensão**.

Repare que alguns campos são, praticamente, autoexplicativos.

**Versão**: identifica a versão do protocolo. No caso do IPv6, o valor desse campo é, sem grandes surpresas, o valor 6.

**Limite de Encaminhamento**: campo cujo valor é diminuído a cada salto (_**hop**_) de roteamento. Serve para que, caso ocorra um _**loop**_ na rede, o pacote possa ser descartado após ?passar? por um certo número de roteadores; similar ao que acontecia como campo TTL, no IPv4, mas cujo significado fica mais claro agora.

**Endereço de Origem**: possui o endereço de origem do pacote.

**Endereço de Destino**: possui o endereço de destino do pacote.

Outros, ainda sim, não são tão intuitivos:

**Classe de Tráfego**: serve para identificar os pacotes por classes de serviços ou prioridade. Por exemplo, um pacote cujo conteúdo é uma mensagem de áudio ou vídeo e, por consequência, afetado pelo atraso na entrega, necessita de uma prioridade maior que outros tipos de pacotes.

**Identificador de Fluxo**: serve para facilitar a aplicação de regras aos pacotes que tenham um mesmo destino (em geral, uma mesma aplicação ou software que irá consumi-lo).

**Tamanho dos Dados**: serve para sinalizar a quantidade de bytes úteis.

Quando dizemos, no contexto de redes de computadores, bytes úteis, estamos nos referindo ao ?pedaço? de um arquivo pdf, de um áudio, de um vídeo, etc.; que está contido no pacote. Essa informação também aparece muito em seu termo inglês, _**payload**_. O pacote contém outras informações que, em si, não são fazem parte da informação que desejamos transmitir, como o próprio cabeçalho IP, por exemplo: o que nos interessa transmitir de um PC para outro é o arquivo em si, e não dados de controle ? embora sabemos que esses dados são necessários para que a rede funcione adequadamente, certo?

**Próximo Cabeçalho**: serve para indicar qual o cabeçalho de extensão que deve ser lido na sequência.

![[Screenshot_from_2021-10-22_23-04-56.png]]

![[Screenshot_from_2021-10-22_23-05-14.png]]

![[Screenshot_from_2021-10-22_23-05-21.png]]

![[Screenshot_from_2021-10-22_23-05-35.png]]

![[Screenshot_from_2021-10-22_23-05-47.png]]

![[Screenshot_from_2021-10-22_23-05-57.png]]

![[Screenshot_from_2021-10-22_23-06-05.png]]

![[Screenshot_from_2021-10-22_23-06-13.png]]

![[Screenshot_from_2021-10-22_23-06-22.png]]

**Cabeçalhos de extensão**

Os cabeçalhos de extensão foram criados para fins de otimização da comunicação, uma vez que, a maioria das informações contidas nestes são de interesse apenas dos dispositivos finais (como PCs e servidores), não necessitando serem lidos e analisados pelos dispositivos intermediários (roteadores).

Assim, os cabeçalhos devem ser enviados em uma ordem pré-determinada para evitar que dispositivos intermediários tenham que processar todo o conjunto de cabeçalhos para decidir se são destinados a eles ou não. Logo, os cabeçalhos destinados a todos os dispositivos devem ser colocados antes daqueles relevantes apenas para o destinatário final.

A título de curiosidade, o IPv6 atualmente define 6 cabeçalhos de extensão (embora novos cabeçalhos estão em estudo). São eles:

_**Hop-by-Hop**_: alocado imediatamente após o cabeçalho base do IPv6, indica se o pacote deve ser processado ou descartado. Caso esse cabeçalho de extensão não exista, os dispositivos intermediários saberão que devem utilizaram apenas as informações do cabeçalho base do IPv6.

_**Routing**_: atualmente utilizado para informações de roteamento em dispositivos móveis (sem fio).

_**Fragmentation**_: identifica se o pacote foi “quebrado” em pedaços menores, por conta da incapacidade do destino em receber dados maiores.

A capacidade máxima (tamanho) de dados que um dispositivo pode processar é chamada de MTU.

_**Authentication Header**_ e _**Encapsulating Security Payload**_: ambas extensões contém informações relacionadas ao protocolo de tunelamento IPSec, muito utilizado em VPNs (Virtual Private Networks).

_**Destination Options**_: também utilizado para informações de roteamento em dispositivos móveis (sem fio).

**Conclusão**

Neste capítulo apresentamos:

- As melhorias implementadas no protocolo IPv6;
- A explicação de cada campo (atributo) do cabeçalho IPV6;
- Uso e tipos de cabeçalhos de extensão.