### **Introdução**

O acesso a impressoras na rede é uma das atividades mais comuns no ambiente computacional. Manter o acesso aos recursos de impressão de forma segura e confiável é um dos desafios de quem gerencia um ambiente de rede baseado no Windows. Para fornecer acesso aos recursos de impressão em uma rede, devemos entender como configurar e conceder de maneira apropriada o uso desse recurso dentro do servidor.

Nessa aula iremos entender, habilitar e configurar serviços de impressão no Windows Server 2012 e aprender considerações importantes e práticas recomendadas para trabalhar com os serviços de impressão.

### **Impressão pela rede**

Quando utilizamos a função Serviços de Impressão e Documentos no Windows Server 2012, podemos compartilhar impressoras em uma rede e centralizar o gerenciamento do servidor de impressão e da impressora de rede. Ao usar o console Gerenciamento de Impressão, podemos monitorar as filas de impressão e receber notificações importantes referentes à atividade do servidor de impressão.

### **Instalando o serviço de impressão**

A função Serviços de Impressão e Documentos é adicionado ao servidor quando desejamos que ele se torne um servidor de impressão. O serviço de servidor de impressão inclui o console de gerenciamento de impressão que será utilizado para a maioria das tarefas de gerenciamento no servidor de impressão, podendo através dele gerenciar várias impressoras e até mesmo vários servidores de impressão.

### **Adicionando a função Serviços de Impressão e Documentos**

Através do Gerenciador do Servidor, podemos adicionar a função Serviços de Impressão e Documentos de uma forma bem simples. A única escolha que precisamos fazer é quais serviços adicionar. Podemos usar as seguintes etapas para adicionar a função em um servidor Windows:

1. No Gerenciador de Servidor, clique em Adicionar funções e recursos.

2. Selecione Instalação baseada em função ou recurso e clique em Avançar.

3. Selecione o um servidor do pool de servidores e clique em Avançar.

4. Na página Selecionar Funções do servidor, selecione Serviços de Impressão e Documentos; clique em Avançar.

5. Como mostrado na Figura 1, uma janela será aberta solicitando que adicionemos as Ferramentas de Administração de Funções, clique em Adicionar Recursos para continuar e em seguida clique em Avançar.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259204/14920.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259204/14920.jpg)

Figura 1: Adicionar função Serviço de Impressão e Documentos

6. Na página Serviços de Função Serviços de impressão será selecionada por padrão; clique em Avançar para continuar.

7. Clique em Instalar na página Confirmação.

8. Quando a instalação estiver concluída, clique em Fechar.

Depois de adicionar a função Serviço de Impressão e Documentos, acesse a função Serviços de Impressão no Gerenciador do Servidor.

### **Trabalhando no Console de Gerenciamento de Impressão**

O console de Gerenciamento de Impressão é um ótimo complemento para a interface do sistema operacional, permitindo desenvolver as tarefas relacionada a impressão de uma forma centralizada e ainda incluindo o seguinte:

- Adicionar novos drivers
- Visualizar impressoras, utilizam filtros personalizados
- Gerenciar as configurar drivers de impressoras
- Monitorar o estado da impressora e configurar alertas
- Conectar a servidores de impressão remotos

O Console de Gerenciamento de Impressão é dividido em três sessões principais. A Figura 2 mostra as três sessões existentes no Console de Gerenciamento de Impressão.

- Filtros personalizados: Os filtros permitem visualizar e gerenciar todas as impressoras e a partir desse console, independentemente de qual servidor de impressão que está conectado.
- Servidores de Impressão: Exibe os servidores de impressão existente. No entanto, se a organização tem vários servidores de impressão, é possível gerenciá-los todos através de um único console.
- Impressoras Implantadas: Exibe as impressoras que foram implantadas usando Diretiva de Grupo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259205/14922.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259205/14922.jpg)

Figura 2: Sessões do Console de Gerenciamento de Impressão.

### **Adicionando novas impressoras**

Utilizamos o Console de Gerenciamento de Impressão para adicionar novas impressoras, permitindo usá-lo para detectar automaticamente as impressoras na mesma sub-rede do servidor de impressão. Ao clicar com o botão direito em Impressoras e selecione Adicionar impressora, como mostrado na Figura 3. Além disso, observamos os quatro métodos de instalação:

- Procurar impressoras na rede: Este método permite detectar automaticamente impressoras.
- Adicionar uma impressora TCP/IP ou Serviços da Web pelo endereço IP ou nome do host: Se a impressora estiver em uma sub-rede separada ou configurada como uma impressora de serviços web (disponível a partir de um servidor da Web), use esta opção para adicionar manualmente o endereço IP ou nome de host da impressora.
- Adicionar uma nova impressora utilizando uma porta existente: Se uma porta já existe, podemos usar esse método para adicionar uma impressora a uma porta existente.
- Criar uma nova porta e adicionar uma nova impressora: Este método permite criar novas portas e adicionar impressoras para elas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259207/14923.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259207/14923.jpg)

Figura 3: Adicionar impressora.

As impressoras conectadas à porta USB do servidor não precisam de quaisquer medidas adicionais. Basta ligar a impressora à porta USB que ela será automaticamente detectada, e o driver será adicionado. Por padrão essa impressora não sera compartilhada, mas podemos acessar as propriedades da impressora e compartilhá-la a partir da guia Compartilhamento.