[![](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)

Você se lembra do desafio proposto no início da aula? Agora, acompanhe aqui a resolução.

**1.** A implementação do chat com mensagens de texto pode ser realizada utilizando sockets e um modelo de comunicação entre processos cliente-servidor. No contexto desta atividade, o cliente e o servidor poderiam ter as seguintes características:

- **Servidor**: é o processo que centraliza todas as mensagens (requisições) de clientes recebidas via _socket_. Tem como responsabilidade o envio de mensagem com resposta a cada requisição recebida. Quando uma requisição chega ao servidor, é criado um _thread_ para atender àquela requisição.**Cliente**: o usuário cria uma instância do processo cliente que faz uma requisição ao servidor via _socket_. Na requisição do cliente, são informados o endereço do servidor e a respectiva porta.

O servidor do chat utiliza _sockets_ e aguarda por conexões de clientes. A cada cliente que requisita uma conexão, é criado um novo _thread_ para controle dele.

O cliente é formado por um processo principal, o qual habilita o console para envio de mensagens, porém há um _thread_ que aguarda por mensagens que venham do servidor, as quais vieram de outros clientes.

**2**. Para qual tipo de dispositivo deve ser implementada a parte da aplicação que tem o processo cliente? E para o processo servidor?

A parte cliente da aplicação deve ser implementada para smartphone com acesso via navegador ou aplicativo instalado localmente, já que permite acesso mais fácil por motoristas. Para haver conexão com o servidor, o smartphone deverá ter acesso à internet por rede de dados celulares ou rede sem fio.

A parte servidor da aplicação deverá ser implementada para uma máquina que tenha maior capacidade de processamento e que deverá executar em alta disponibilidade (24 horas por dia, 7 dias por semana).

**3.** Como poderá ser implementada a comunicação realizada entre os colaboradores? Pense na linguagem de programação, na biblioteca ou API e como coordenar a troca das mensagens.

A comunicação poderá ser implementada utilizando API de _sockets_ da linguagem adotada pela empresa para desenvolvimento, como C++, Python ou Java. A troca de mensagens é realizada passando pelo gerenciamento do servidor que coordena a ordem das mensagens.

**4.** Como o servidor poderá ser implementado para atender a um número maior de conexões?

O servidor poderá ser implementado usando vários threads de execução para atender às requisições dos clientes.

Nesta aula, você aprendeu sobre a utilização de processos e _threads_ no contexto de sistemas distribuídos, como ocorre a comunicação entre processos, processos cliente e servidor e _sockets_. Agora, você é capaz de entender melhor as aplicações existentes, identificar quais são cliente-servidor e aplicar estes conceitos em aplicações em desenvolvimento de forma a ter melhor desempenho. Bons estudos!