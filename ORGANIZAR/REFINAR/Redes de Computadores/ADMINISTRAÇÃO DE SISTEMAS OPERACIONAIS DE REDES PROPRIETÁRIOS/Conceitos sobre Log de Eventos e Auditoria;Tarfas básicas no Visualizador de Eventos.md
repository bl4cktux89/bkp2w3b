### **Introdução**

Como administrador, precisamos estar atentos aos sistemas conectados em rede. O status ou uso dos recursos do sistema podem mudar drasticamente ao longo do tempo, onde serviços podem parar sua execução, o discos podem ficar sem espaço, os aplicativos podem gerar exceções que, por sua vez, podem causar problemas no sistema, usuários não autorizados podem tentar invadir o sistema. As técnicas discutidas nesta aula podem ajudar a identificar e resolver estes e outros problemas do sistema.

### **Gerenciando aplicativos, processos e desempenho**

Toda vez que um aplicativo é iniciado ou quando um programa de linha de comando é executado, o Microsoft Windows Server inicia um ou mais processos para lidar com o programa relacionado. Geralmente, os processos que iniciam dessa maneira são chamados de processos interativos, ou seja, são processos que iniciam de forma interativa com o teclado ou mouse.

### **Gerenciador de Tarefas**

A ferramenta chave usada para gerenciar processos e aplicações do sistema é o Gerenciador de Tarefas. Podemos usar qualquer uma das seguintes técnicas para exibir o Gerenciador de tarefas:

- Pressione Ctrl + Shift + Esc.
- Pressione Ctrl + Alt + Del, e, em seguida, toque ou clique em Gerenciador de tarefas.
- Clicar com botão direito do mouse na barra de tarefas e, em seguida, clicar no atalho Gerenciador de Tarefas.

### **Registro de Eventos e Visualização**

Os Logs de eventos fornecem informações significativas que podem ajudar a rastrear problemas de sistema e de segurança, além de controlar como os eventos são monitorados. Quando iniciamos este serviço, podemos acompanhar as ações do usuário e eventos de uso de recursos por meio de logs de eventos. Dois tipos gerais de log são usados:

- Logs do Windows: Os logs que o sistema operacional usa para registrar eventos do sistema gerais relacionados a aplicativos, segurança, configuração e componentes do sistema.
- Logs de Aplicativos e serviços: Logs que os aplicativos e serviços usam para armazenar eventos específicos de serviço ou de aplicativo.

O Log do Windows ainda contém, como observado na Figura 1 os seguintes logs específicos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/7/264777/14962.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/7/264777/14962.jpg)

Figura 1: Visualizador de Eventos

- Aplicativo: Este log de registro grava eventos registrados por aplicativos, como a falha do de SQL Server ao tentar acessar um banco de dados. O local padrão é %SystemRoot%\System32\Winevt\Logs\Application.evtx.
- Segurança: Este Log armazena definições para a auditoria com as políticas de grupo locais ou globais. O local padrão é %SystemRoot%\System32\Winevt\Logs\Security.evtx.
- Instalação: Este log registra eventos registrados pelo sistema operacional ou seus componentes durante a configuração e instalação. O local padrão é %SystemRoot%\System32\Winevt\Logs\Setup.evtx.
- Sistema: Este log registra eventos registrados pelo sistema operacional ou seus componentes, tais como a falha de um serviço para iniciar na inicialização. O local padrão é %SystemRoot%\System32\Winevt\Logs\System.evtx.
- Eventos encaminhados: Quando o encaminhamento de evento é configurado, estes registros de log de eventos são enviados de outros servidores. O local padrão é %SystemRoot%\System32\Config\ForwardedEvents.evtx.

### **Acessando eventos através do Gerenciador do Servidor**

Quando trabalhamos com o Gerenciador do Servidor e selecionamos o nó Todos os Servidores, no painel central encontraremos Eventos, como a mostrada na Figura 2, podemos usar esse painel da seguinte forma:

1. Para um servidor conectado localmente, podemos usar o painel de eventos no nó de servidor local ou no nó Todos os Servidores para visualizar os eventos, avisos e erros recentes relacionados a aplicação e logs de sistema.

2. Nós de grupo por servidor, são organizados por funções de servidor, como o AD DS ou DNS, onde podemos visualizar os eventos de erro e aviso recentes em registros relacionados com a função de servidor

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/7/264776/14963.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/7/264776/14963.jpg)

Figura 2: Eventos

As colunas no painel de Eventos podem ser ajustadas quando clicamos com o botão direito em qualquer cabeçalho de coluna e, em seguida, clicamos nas colunas para adicionar ou remover. As colunas incluem:

- Nome do Servidor: O nome do servidor no qual o serviço está sendo executado.
- ID: Geralmente, um identificador numérico para o evento específico, o que poderia ser útil ao pesquisar em bases de conhecimento.
- Severidade: O nível do evento como um erro ou aviso.
- Origem: Aplicativo, serviço ou componente que registrou o evento.
- Log: Em qual log o evento foi gravado.
- Data e Hora: A data e hora do evento foi gravado.

### **Acessando eventos no Visualizador de eventos**

Para trabalhar com logs de eventos em servidores locais podemos acessá-los, seguindo estes passos:

1. No Gerenciador de servidores, selecione Todos os Servidores ou qualquer nó do grupo de servidores no painel esquerdo.

2. No painel Servidores, pressione botão direito do mouse no servidor ao qual você deseja se conectar.

3. Clique em Gerenciamento do computador para se conectar automaticamente ao servidor selecionado.

4. Em Gerenciamento do Computador, visualizamos e trabalhamos com os logs de eventos, expandindo o nó Ferramentas do sistema e, em seguida, selecionando o nó Visualizador de eventos como mostrado na Figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/7/264775/14965.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/7/264775/14965.jpg)

Figura 3: Visualizar eventos

5. Expanda o nó Eventos e visualize os logs de eventos do servidor em das seguintes maneiras:

- Para visualizar todos os erros e avisos para todos os logs, expanda Modos de Exibição Personalizado e, em seguida, selecione Eventos Administrativos. No painel principal, visualize uma lista de todos os eventos de aviso e de erro para o servidor.
- Para visualizar todos os erros e avisos para uma função de servidor específica, expanda Modos de Exibição Personalizado, expanda Funções do Servidor, em seguida, selecione os eventos relacionados as funções. No painel principal, uma lista de todos os eventos para a função selecionada será exibida.
- Para ver os eventos em um log específico, expanda o nó Logs do Windows, em seguida selecione o registro que deseja visualizar, como por exemplo Aplicativo ou Sistema.

6. Use as informações na coluna Fonte para determinar qual serviço ou processo registado um evento particular.

Como mostrado na Figura 4, as entradas no painel principal do Visualizador de eventos fornecer uma visão geral de quando, onde, e como um evento ocorreu. Para obter informações detalhadas sobre um evento, reveja os detalhes fornecidos na guia Geral na parte inferior do painel principal.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/7/264774/14965.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/7/264774/14965.jpg)

Figura 4: Eventos da função de servidor DHCP

O nível do evento ou palavra-chave precede a data e hora do evento. Níveis de eventos incluem o seguinte:

- Informações: Um evento informativo, que está geralmente relacionada a uma ação bem-sucedida.
- Auditoria: Um evento relatando o êxito ou a execução bem sucedida de uma ação.
- Falha de auditoria: Um evento relatando a falda de execução de uma ação.
- Aviso: Um aviso detalhando a prevenção de problemas futuros no sistema.
- Erro: Um erro não-crítico, como a falha de um pedido de transferência de zona DNS em um servidor DNS.
- Crítico: Um erro crítico, tais como o serviço de cluster sendo desligados.

Além de nível, data e hora registradas, as entradas de sumários e de eventos detalhada fornecer as seguintes informações:

- Fonte: O aplicativo, serviço ou componente que registrou o evento.
- Id do Evento: Geralmente, um identificador numérico para o evento específico, o que poderia ser útil ao pesquisar bases de conhecimento.
- Categoria da tarefa: A categoria do evento, que é quase sempre definida como Nenhum, mas às vezes é usado para descrever a ação relacionada, a um processo ou um serviço.
- Usuário: A conta de usuário que estava conectado quando o evento ocorreu.
- Computador: O nome do computador em que o evento ocorreu.
- Descrição: Informações de entradas detalhadas.
- Dados: Entradas detalhadas, qualquer saída de dados ou código de erro pelo gerado pelo evento.

### **Limpando os logs de eventos**

Quando um log de eventos está cheio, precisamos limpá-lo e para fazer isso através do Gerenciamento do computador, siga estes passos:

1. Expanda Logs do Windows ou aplicações e serviços Logs, conforme apropriado para o tipo de registro que você deseja configurar. Agora você deve ver uma lista de logs de eventos.

2. Clique com o botão direito o log de eventos cujas propriedades você deseja definir e, em seguida, clique em Limpar Log no menu de atalho.

3. Clique em Salvar, caso queira armazenar uma cópia do registo antes de o limpá-lo, senão, escolha Limpar e continue sem salvar o arquivo de log.

### **Arquivamento de logs de eventos**

Em alguns sistemas, tais como controladores de domínio ou servidores de aplicativos, é importante manter arquivado por períodos, informações mantidas nos logs. No entanto, normalmente não é prático definir o tamanho máximo do registo. Em vez disso, devemos permitir que o Windows arquive periodicamente os logs de eventos, ou devemos arquivar manualmente os logs de eventos. Os logs podem ser arquivados em quatro formatos:

Arquivos de Eventos (.evtx): formato para o acesso no Visualizador de eventos.

Texto separados por tabulação (.txt): Para o acesso em editores de texto ou processadores de texto ou importar para planilhas e bancos de dados.

Texto (.csv):Delimitados por vírgula para importação em planilhas ou bancos de dados.

Formato XML (.xml): Salvar como um arquivo XML