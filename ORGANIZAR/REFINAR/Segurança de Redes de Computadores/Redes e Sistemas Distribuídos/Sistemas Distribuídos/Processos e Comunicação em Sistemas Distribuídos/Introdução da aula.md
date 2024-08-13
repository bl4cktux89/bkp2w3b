[![](https://ampli-images.s3.amazonaws.com/production/201e3c5b-6747-43f5-aa8f-f63b7d155cf6/original)](https://ampli-images.s3.amazonaws.com/production/201e3c5b-6747-43f5-aa8f-f63b7d155cf6/original)

### **Qual é o foco da aula?**

Nesta aula, você aprenderá conceitos importantes, os quais permitirão a construção de sistemas distribuídos eficientes.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- identificar o conceito de processos _threads_ e processos cliente-servidor;
- examinar as características de comunicação entre processos e em grupos;
- analisar os conceitos de _sockets_.

**Introdução da aula**

O avanço da tecnologia utilizada em processadores tem permitido a geração de processadores para dispositivos cada vez menores, como _smartwatches_. Os smartphones possuem uma grande capacidade de processamento, permitem o acesso à internet e a execução de jogos e de vários outros aplicativos que demandam uso de processamento. Os notebooks e desktops também possuem processadores com múltiplos núcleos de processamento.

Os sistemas operacionais são adaptados e atualizados periodicamente, para adquirir a capacidade de gerenciar essas alterações nos processadores. E quanto aos sistemas web, você sabe como devem ser implementados para utilizar essa capacidade de processamento? O processamento sequencial é suficiente para utilizar mais de um núcleo de processamento?

Esta aula nos leva a refletir sobre como os sistemas distribuídos estão inseridos neste contexto de avanço das tecnologias e como os sistemas web são desenvolvidos. Os conceitos de processos e _threads_ são utilizados para permitir a implementação de sistemas que melhor utilizem o processamento dos núcleos de processamento, que podem estar em uma mesma máquina ou em máquinas remotas. Quando os processos são executados em máquinas remotas, a comunicação torna-se necessária para realizar a troca de informação entre eles. Essa comunicação pode ocorrer somente entre dois processados ou entre todos os processos de um grupo.

Sistemas web, como comércio eletrônico, correio eletrônico, máquinas de busca, entre outros, são exemplos de sistemas distribuídos. Eles possuem o lado do cliente (o usuário), que requisita um serviço, e o lado do servidor, que processa a requisição e devolve a resposta para o cliente. Mas, você sabe como ocorre essa “conversa” entre cliente e servidor em termos de sistema web? Será que cliente e servidor estão executando na mesma máquina ou em máquinas diferentes? O cliente é um processo, e o servidor, outro processo. Eles podem executar em uma mesma máquina ou em máquinas remotas.

Considerando o exemplo de um sistema de máquina de busca, por exemplo, o buscador Google, você pode se interessar pela busca na internet por páginas com ocorrências do termo “pulseira inteligente”. Ao abrir um navegador na sua máquina (smartphone, notebook, desktop, servidor, entre outros), iniciará a execução de um processo. Ao digitar o termo e pedir para buscar, esse processo comunica-se via rede com um processo servidor, que estará em uma máquina remota e fará a busca de todos os endereços de páginas na internet onde o termo está ocorrendo. Em seguida, a resposta da busca retornará para o cliente (sua máquina). Para que todo o processamento seja realizado de forma rápida, várias máquinas são consultadas, as quais guardam informações e possuem processos executando para recuperar a informação.

A comunicação entre dois processos (cliente e servidor) via rede ocorre através de uma interface de software denominada _socket_, que é uma interface entre a camada de aplicação e a de transporte. Um processo envia uma mensagem, a qual é empurrada via socket pela rede e chega ao outro processo, que a lê e realiza alguma ação. Para saber o caminho a ser percorrido na rede, o _socket_ leva ao endereço do processo destino. Após a troca de várias mensagens, os sistemas web conseguem atender o usuário, gerando a informação solicitada, permitindo concluir uma compra on-line, realizar uma conversa entre duas ou mais pessoas, entre outras ações.

Imagine que você foi contratado como _trainee_ de uma empresa de transportes de mercadorias que atua em todo o Brasil. Essa empresa possui mais de 200 colaboradores, sendo 100 deles motoristas de caminhão. Foi atribuída a você a tarefa de auxiliar a equipe de desenvolvimento na elaboração de uma solução utilizando os conceitos de processos, _threads_ e _sockets_, a fim de implementar um chat (aplicação de conversação) que permita que os motoristas troquem mensagens de texto. Neste contexto, elabore um relatório que responda a todas as questões a seguir e, após isso, crie uma apresentação da solução do problema:

1. Como você implementaria o chat no modelo cliente-servidor?
2. Para qual tipo de dispositivo deve ser implementada a parte da aplicação que tem o processo cliente? E para o processo servidor?
3. Como poderá ser implementada a comunicação realizada entre os colaboradores? Pense na linguagem de programação, na biblioteca ou API e como coordenar a troca das mensagens.

Como o servidor poderá ser implementado para atender a um número maior de conexões?

O entendimento sobre o funcionamento dos sistemas web, como os processos se comunicam e como implementar sistemas mais eficientes utilizando esses conhecimentos é de fundamental importância na formação do analista de sistemas. Portanto, vamos nos aprofundar um pouco mais nesses conceitos. Bons estudos!