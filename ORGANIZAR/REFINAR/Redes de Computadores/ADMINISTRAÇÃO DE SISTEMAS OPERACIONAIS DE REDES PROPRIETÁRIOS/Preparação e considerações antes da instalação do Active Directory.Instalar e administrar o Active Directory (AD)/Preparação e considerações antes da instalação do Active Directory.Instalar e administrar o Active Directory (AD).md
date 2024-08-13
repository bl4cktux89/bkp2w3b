### **Introdução**

O Serviços de Domínio do Active Directory (AD DS) e seus serviços relacionados formam a base para as redes corporativas que executam sistemas operacionais Windows. Segundo a Microsoft (2012), o banco de dados do AD DS é o repositório central de todos os objetos do domínio, como contas de usuário, contas de computador e grupos. Neste tópico vamos aprender a instalar essa importante funcionalidade, demonstrando o processo de uso do Gerenciador do Servidor para instalar o AD DS em um computador local.

### **Antes de iniciar a instalação**

Em versões anteriores ao Windows Server 2012, era comum usar a ferramenta dcpromo.exe para instalar controladores de domínio. Mas ao tentar utilizar essa ferramenta em um servidor Windows Server 2012, a seguinte mensagem de erro será exibida: “O Assistente de Instalação dos Serviços de Domínio do Active Directory foi realocado no Gerenciador do Servidor”. Isso porque a ferramenta foi substituída pelo Gerenciador do Servidor.

### **Instalando um controlador de domínio através da ferramenta Gerenciador do Servidor**

Com o Windows Server 2012, as tarefas de instalação e configuração Serviços de Domínio Active Directory são realizadas através da ferramenta **Gerenciador do Servidor**. Não é mais necessário executar o assistente para adicionar a função e realizar a instalação e uma tarefa separada. Em vez disso, utilizamos um Assistente de Configuração para adicionar a função do Active Directory Domain Services e, em seguida, promover o servidor para um controlador de domínio.

Ao executar o Gerenciador do Servidor, podemos escolher se a operação será executada no computador local, em um computador remoto ou por membros de um pool de servidores. Em seguida, adicionamos a função AD DS. Ao término do processo de instalação inicial, os binários do AD DS são instalados, mas o AD DS ainda não está configurado no servidor. Uma mensagem nesse sentido é exibida no Gerenciador do Servidor.

Selecione o link para **Promover este servidor a um controlador de domínio** e, em seguida, o Assistente de Configuração dos Serviços de Domínio do Active Directory é executado. Será necessário fornecer as informações listadas na tabela a seguir:

![[Screenshot_from_2022-03-31_00-54-17.png]]

Algumas informações adicionais são necessárias antes de executar a promoção do controlador de domínio, observe a tabela a seguir.

![[Screenshot_from_2022-03-31_00-55-00.png]]

Os passos básicos para instalação são os seguintes:

1. No Gerenciador do Servidor, clique em Gerenciar e, em seguida, clique em Adicionar funções e recursos. Isso inicia o assistente Adicionar funções e recursos

2. Na página Selecionar Tipo de Instalação, selecione instalação baseado em recursos e clique em Avançar.

3. Na página Selecionar servidor de destino, o pool de servidores mostra servidores que foi adicionado para o gerenciamento. Clique no servidor que está sendo configurado, e em seguida, clique em Avançar.

4. Na página Selecionar Funções do Servidor, selecione Serviços de Domínio Active Directory e, em seguida, clique em Avançar duas vezes. Clique em Instalar. Isso executa o Assistente de Configuração de Serviços de Domínio Active Directory.

5. Quando a tarefa de instalação inicial for concluída, clique em **Promover este servidor a um controlador de domínio** para iniciar o Assistente de Configuração de Serviços de Domínio Active Directory.