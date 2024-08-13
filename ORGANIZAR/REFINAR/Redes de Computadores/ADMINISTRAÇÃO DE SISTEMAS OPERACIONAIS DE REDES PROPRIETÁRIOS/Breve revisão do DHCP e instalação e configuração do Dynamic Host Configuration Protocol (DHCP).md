### **Introdução**

Ao utilizar o Dynamic Host Configuration Protocol (DHCP) é possível simplificar a administração de domínios do Active Directory, isso por que ele é utilizado para atribuir dinamicamente as informações de configuração TCP/IP aos clientes da rede. Entre os benefícios oferecidos, podemos destacar a redução de tempo para realizar a configuração do sistema, além de fornecendo um mecanismo centralizado para a atualização das configurações.

Nessa aula, vamos compreender os benefícios oferecidos pelo DHCP e também realizar a instalação e configuração dessa funcionalidade.

### **Entendendo o DHCP**

O DHCP permite controlar de forma centralizada o endereçamento IP, isso porque, uma vez instalado no servidor, ele fornecerá as informações de rede necessárias para os computadores cliente, o que pode incluir, endereço IP, máscara de sub-rede, gateway padrão, informações do domínio primário e secundário para o servidor de Domain Name System (DNS), informações primária e secundária do Windows Internet Name Service (WINS).

Os servidores DHCP podem atribuir configurações de endereços de forma dinâmica para o protocolo IP versão 4 (IPv4), IP versão 6 (IPv6), ou ambos endereços a qualquer uma das placas de interface de rede (NICs) em um computador.

### **Usando endereçamento dinâmico IPv4**

Um computador que utiliza uma configuração de endereçamento dinâmico IPv4 é chamado de cliente DHCP. Quando um computador cliente DHCP inicializa, um endereço IPv4 de 32 bits pode ser recuperado a partir de um pool de endereços IPv4 definidos em um servidor DHCP da rede, esse endereço é atribuído ao cliente por um período de tempo especificado conhecido como concessão.

### **Instalando um servidor DHCP**

O endereçamento dinâmico IP está disponível somente se um servidor DHCP é instalado na rede, sendo assim, usando o assistente em Adicionar funções e recursos é possível instalar a função do servidor DHCP, e configurar suas definições iniciais e também autorizar o servidor no Active Directory. Levando em consideração que somente os servidores DHCP autorizados podem fornecer endereços IP dinâmicos aos clientes.

### **Instalando os componentes do DHCP**

Em um servidor executando o Windows Server 2012, siga os passos informados abaixo para habilitar o a função DHCP no servidor. Certifique-se de que o seu servidor tenha um endereço IPv4 definido de forma manual.

1. No Gerenciado de servidor, clique em Gerenciar e, em seguida, clique em Adicionar funções e recursos, ou selecione Adicionar funções e recursos no painel de Inicialização Rápida. Isso inicia o assistente para Adicionar funções e recursos. O assistente exibirá a página de boas-vindas Antes de começar, após leitura do texto, clique em Avançar.
2. Na página Selecionar Funções, selecione Servidor DHCP. Se recursos adicionais forem necessários para instalar uma função, aparecerá uma caixa de diálogo adicional. Clique em Adicionar Recursos para fechar a caixa de diálogo e adicionar os recursos necessários para a instalação do servidor. Quando estiver pronto para continuar, clique em Avançar três vezes.
3. Depois de rever as opções de instalação e salvá-las, clique em Instalar para iniciar o processo de instalação. A página Progresso da instalação acompanha o andamento da instalação. Quando concluir a instalação da função Servidor DHCP, a página Progresso da instalação será atualizada. Revise os detalhes da instalação para garantir que todas as fases da instalação foram concluídas com êxito.
4. Como indicado no painel de tarefas de configuração pós-implantação, as configurações adicionais são necessárias para o servidor DHCP. Clique no link Configuração Completa DHCP para iniciar o Assistente de Configuração de DHCP de pós-instalação.
5. Na página de autorização, para especificar as credenciais a serem usadas para autorizar o servidor DHCP no Active Directory, verifique se o nome do usuário exibido tem privilégios de administrador no domínio que o servidor DHCP faz parte. Se o usuário em questão é um administrador, clique em aceitar para autorizar o servidor.
6. Para concluir a instalação, é necessário configurar opções do servidor para atribuir definições de configuração comuns para clientes DHCP, incluindo **003 Router**, **006 servidores DNS**, **015 DNS Domain Name**, e **044 WINS / NBNS Servers**.

Depois de instalar o serviço do servidor DHCP, o console DHCP está disponível em Gerenciador de Servidores. Clique em Ferramentas e, em seguida, clique em DHCP para abrir o console DHCP, mostrado na Figura 1. A janela principal está dividida em dois painéis. O painel esquerdo lista os servidores DHCP no domínio de acordo com o seu nome de domínio totalmente qualificado (FQDN). O painel da direita mostra a visão expandida da seleção atual.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/8/262840/14093.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/8/262840/14093.PNG)

Figura 1: console DHCP

### **Iniciando ou Parando um Servidor DHCP**

É possível iniciar, parar, pausar e retomar o serviço do servidor DHCP através do console de gerenciamento do DHCP. Para isso, clique com o botão direito do mouse no servidor que deseja gerenciar no console DHCP, aponte para Todas as tarefas, e em seguida, clique em iniciar, parar, pausar, retomar ou reiniciar conforme necessário.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/8/262841/14094.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/8/262841/14094.PNG)

Figura 2: Serviços DHCP

### **Autorizando servidores DHCP no Active Directory**

Antes de utilizar um servidor DHCP em um domínio, é necessário autorizá-lo no servidor Active Directory, dessa forma ele poderá realizar sua tarefa. No console do DHCP, qualquer servidor DHCP não autorizado terá um ícone que mostra uma seta para baixo vermelha, no entento, os servidores DHCP autorizados têm um ícone que mostra uma seta verde para cima e estão prontos para funcionar.

No console do DHCP, para autorizar um servidor DHCP, clique com o botão direito na entrada do servidor e, em seguida, selecione Autorizar. Para retirar a autorização, clique com o botão direito no servidor e selecione Desautorizar.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/8/262842/14096.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/8/262842/14096.PNG)

Figura 3: Autorizar um servidor DHCP

### **Escopos no servidor DHCP**

Um escopo DHCP é um intervalo de endereços IP disponíveis para concessão e que são gerenciados por um servidor DHCP. Por exemplo, um escopo DHCP para a rede 192.168.0.0 com máscara de sub-rede 255.255.255.0, tem disponível em seu intervalo de endereços IPs, o primeiro endereço 192.168.0.1 até o ultimo 192.168.0.254. Se um computador cliente nessa sub-rede solicita um endereço IP, o servidor poderá escolher um endereço IP nesse intervalo e aloca-lo ao cliente.

### **Configurando um escopo no servidor DHCP**

Para criar um escopo usando endereços IPv4, siga estes passos:

1. No console do DHCP, expanda o nó para o servidor, em seguida, clique com o botão direito sobre IPv4.

2. No menu de atalhos, clique em Novo Escopo. Isso inicia o Assistente para novos escopos. Clique em Avançar.

3. Digite um nome e descrição para o escopo, e em seguida, clique em Avançar.

4. Nas caixas de endereço, como mostrado na figura 4, defina o endereço IP inicial e o endereço IP final.  Por exemplo, 192.168. 0.1 e 192.168. 0.254.

5. Defina a máscara de sub rede como padrão, por exemplo, 255.255.255.0 e em seguida, clique em Avançar.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/8/262843/14113.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/8/262843/14113.PNG)

Figura 4: Intervalos de endereços IP

6. Use as caixas de Endereço IP e endereço final IP para adicionar Exclusões e em seguida, clique em Avançar.

7. Especificar a duração do período de concessão, usando o Dia (s), hora (s) e Minutos caixas e em seguida, clique em Avançar.

8. Para configurar as opções DHCP comuns, como DNS, WINS, gateways e outros. Selecione Sim, desejo configurar essas opções agora.

9. A primeira opção que podemos configurar é o gateway padrão. Na caixa Endereço IP, digite o endereço IP do gateway padrão primário, e em seguida, clique em Adicionar.

10. Clique em Avançar. Defina as configurações de DNS padrão para clientes DHCP. Digite o nome do domínio pai, como por exemplo empresa.br,  a ser usado para a resolução de DNS de nomes.

12. Na caixa Endereço IP, digite o endereço IP do servidor DNS primário, por exemplo 192.168.0.1 e, em seguida, clique em Adicionar.

14. Se necessário defina as configurações WINS para os clientes DHCP.

15. Ative o escopo, selecione Sim, desejo ativar este escopo agora e, em seguida, clique em Avançar.

16. Clique em Concluir para concluir o processo.

Pronto, o servidor DHCP está pronto para ser utilizado.