**Chamadas de procedimento remoto**

Este capítulo fornece uma visão geral de chamadas de procedimento remoto (RPC) RPC.

**O que é RPC**

O RPC é uma técnica poderosa para a construção de aplicações distribuídas, baseada em arquitetura cliente-servidor. Baseia-se na noção da chamada procedimento convencional, ou locais, de modo que o procedimento chamado não precisa existir no mesmo espaço de endereços. Os dois processos podem ser no mesmo sistema, ou podem estar em diferentes sistemas com uma rede entre eles, como, por exemplo, a Internet. Usando RPC, os programadores de aplicações distribuídas evitam os detalhes da interface com a rede. A independência do transporte de RPC isola a aplicação dos elementos físicos e lógicos do mecanismo de comunicação de dados e permite que o aplicativo utilize uma variedade de transportes.

RPC faz com que o modelo cliente / servidor de computação fique mais simples e fácil de programar.

**Como funciona a RPC**

Uma RPC é análoga a uma chamada de função. Como uma chamada de função, quando uma RPC é feita, os argumentos de chamada são passados â¿¿â¿¿para o procedimento remoto e o chamador aguarda por uma resposta a ser retornado do procedimento remoto. O cliente faz uma chamada de procedimento que envia uma solicitação para o servidor e espera. O segmento está bloqueado desde o processamento até que uma resposta seja recebida, ou que ela expire. Quando o pedido chega, o servidor chama uma rotina de distribuição que executa o serviço solicitado e envia a resposta para o cliente. Após a chamada RPC é concluída, o programa cliente continua. RPC especificamente suporta aplicações de rede.

Um procedimento remoto é identificado exclusivamente pelo triplo: (número do programa, número da versão, número de procedimento)

- O número do programa identifica um conjunto de procedimentos remotos relacionados, cada um dos quais tem um número único procedimento. Um programa pode consistir de uma ou mais versões.
- Versão é constituída por um conjunto de procedimentos que estão disponíveis para ser chamado remotamente. Os números de versão permitir que múltiplas versões de um protocolo RPC para estar disponível simultaneamente. Cada versão contém o número de procedimentos que podem ser chamados remotamente.
- O procedimento tem um número de procedimento.

![[pic1 3.jpg|pic1 3.jpg]]

  

**O SOAP**

SOAP, _**Simple Object Access Protocol**_, e em português Protocolo Simples de Acesso a Objetos, é um protocolo para troca de informações estruturadas em uma plataforma descentralizada e distribuída.

- SOAP significa **Simple Object Access Protocol.**
- SOAP é um **protocolo de comunicação**.
- SOAP é para **comunicação entre aplicações**.
- SOAP é um simples protocolo baseado em XML para permitir aplicações trocarem informação sobre HTTP ou outro protocolo.

![[pic2 2.jpg|pic2 2.jpg]]

  

Baseia na Linguagem de Marcação Extensível (XML) para seu formato de mensagem além de outros protocolos da Camada de aplicação, mais notavelmente em Chamada de Procedimento Remoto (RPC) e Protocolo de Transferência de Hipertexto (HTTP), para negociação e transmissão de mensagens.

SOAP pode formar a camada base de uma pilha de protocolos de _**web services**_, fornecendo um framework de mensagens básico sob o qual os serviços web podem ser construídos. Este protocolo baseado em XML consiste de três partes:

- um envelope, que define o que está na mensagem e como processá-la;
- um conjunto de regras codificadas para expressar instâncias do tipos de dados definidos na aplicação;
- uma convenção para representar chamadas de procedimentos e respostas.

A especificação define um framework que provê maneiras para se construir mensagens que podem trafegar através de diversos protocolos e que foi especificado de forma a ser independente de qualquer modelo de programação ou outra implementação específica. Por não se tratar de um protocolo de acesso a objetos, o acrônimo não é mais utilizado.

Geralmente servidores SOAP são implementados utilizando-se servidores HTTP, embora isto não seja uma restrição para funcionamento do protocolo. As mensagens SOAP são documentos XML que aderem a uma especificação fornecida pelo órgão W3C. O primeiro esforço do desenvolvimento do SOAP foi implementar RPCs sobre XML.

SOAP – EM 3 PARTES

· Especificação do envelope SOAP

O envelope SOAP XML define regras específicas para encapsular dados sendo transferidos entre computadores. Isto inclui dados específicos da aplicação, tais como nomes de métodos a invocar, parâmetros de métodos, ou valores de retorno. Pode também incluir informação sobre quem deve processar os conteúdos de envelopes, e no caso de falha, como codificar mensagens de erro.

· Regras de Codificação de Dados

Para trocar dados, computadores devem concordar sobre regras para codificar tipos de dados específicos. Por exemplo, como _**float**_ ou _**arrays**_. SOAP inclui seu próprio conjunto de convenções para codificar tipos de dados. A maior parte destas convenções são baseadas sobre a especificação de XML Schemas.

· Convenções RPC

SOAP pode ser usado em uma variedade de sistemas de mensagens. Para mensagens em duas direções _**(two-way messaging)**_, SOAP define uma convenção simples para representar chamadas de procedimento remoto e respostas. Isto habilita uma aplicação-cliente a especificar um nome de método remoto, incluir qualquer número de parâmetros e receber uma resposta do servidor.

- Dividido em duas partes
    - Service Oriented Architecture Protocol:
        - Framework de mensagens
        - Mensagem representa a informação necessária para invocar um serviço ou analisar o resultado de uma chamada e contém informações específicas da definição da interface do serviço.
    - Service Object Access Protocol:
        - um conjunto de regras de codificação para expressar instâncias dos tipos de dados definidos pela aplicação
        - uma convenção para representar RPCs e respostas
        - um conjunto de regras para usar SOAP com HTTP/1.1
        - Define o método de invocação de um objeto remoto

Vantagens

- Pode atravessar firewalls com facilidade.
- Os dados do SOAP são estruturados usando XML. Portanto, as mensagens podem ser compreendidas por quase todas as plataformas de hardware, sistemas operacionais e linguagens de programação.
- Pode ser usado, potencialmente, em combinação com vários protocolos de transporte de dados, como HTTP, SMTP e FTP.
- O SOAP mapeia satisfatoriamente para o padrão de solicitação / resposta HTTP.
- Pode ser usado tanto de forma anônima como com autenticação (nome/senha).

Desvantagem

- Falta de interoperabilidade entre ferramentas de desenvolvimento do SOAP.
- Embora o SOAP tenha amplo suporte, ainda existem problemas de incompatibilidades entre diferentes implementações do SOAP.
- Mecanismos de Segurança
    - O SOAP não define mecanismo para criptografia do conteúdo de uma mensagem SOAP, o que evitaria que outros tivessem acesso ao conteúdo da mensagem.
- Não existe garantia quanto à entrega da mensagem.
    - Quando uma mensagem estiver sendo transferida, se o sistema falhar, ele não saberá como reenviar a mensagem.
- Um cliente SOAP não pode enviar uma solicitação a vários servidores, sem enviar a solicitação a todos os servidores.
- Incapacidade de transportar conteúdo complexo como arquivos de imagens ou sons

Funcionalidades

- Interoperabilidade entre sistemas utilizando linguagens e protocolos padronizados largamente difundidos, como XML e HTTP.
- Permite a comunicação entre sistemas protegidos por firewalls, sem precisar abrir portas adicionais e possivelmente não seguras. Utiliza (na maioria dos servidores) a porta 80.
- SOAP descreve completamente cada elemento na mensagem, facilitando o entendimento e a proteção contra erros.

Estrutura da mensagem

- SOAP baseia-se na troca de mensagens
- Mensagens são vistas como envelopes que as aplicações usam para enviar dados
- Uma mensagem contém duas partes: cabeçalho e corpo. Ambos podem ser divididos em blocos
- SOAP não especifica o que fazer com o cabeçalho e o corpo. Ele somente diz que o cabeçalho é opcional e o corpo mandatório
- Entretanto uso do corpo e cabeçalho são implícitos. Corpo define os dados da aplicação e o cabeçalho define a estrutura