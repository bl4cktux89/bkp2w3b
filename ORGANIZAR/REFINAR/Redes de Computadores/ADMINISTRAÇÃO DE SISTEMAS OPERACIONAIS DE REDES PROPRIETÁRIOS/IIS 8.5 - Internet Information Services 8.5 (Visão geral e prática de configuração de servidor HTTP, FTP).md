### **Introdução**

A função de Servidor Web Internet Information Services (IIS) no Windows Server 2012 oferece uma plataforma segura, com gerenciamento fácil, modular e extensível para a hospedagem confiável de sites, serviços e aplicativos. Com o IIS podemos compartilhar informações com usuários na Internet, em uma intranet ou extranet. Além de permitir o uso do serviço de FTP. Nessa aula iremos aprender a instalar e gerenciar essa funcionalidade.

### **Adicionando a função de servidor Web através do Gerenciador do Servidor.**

A atribuição de uma função não só instala os serviços correspondentes, mas também exige serviços de dependência. Para instalar o IIS, precisamos implantar a função de Servidor Web (IIS) no servidor, como exibido na Figura 1. Como nas versões anteriores, o IIS é composto por vários módulos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260042/15025.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260042/15025.png)

Figura 1: Adicionando a função Servidor Web

Na página Antes de Começar, clique em Avançar.

1. Na página Tipo de Instalação, clique em Avançar.

2. Na página Seleção de Servidor, clique em Avançar para aceitar o destino do servidor como o servidor local.

3. Selecionar Servidor Web (IIS) na página Selecionar Funções do Servidor e clique em Avançar.

3. No pop-up Adição de Funções e Recursos, selecione Adicionar Recursos para instalar também as ferramentas de Gerenciamento IIS no servidor IIS, e em seguida, clique em Avançar.

4. Na página Servidor Web (IIS), clique em Next para avançar o assistente.

5. Na lista de seleção Serviços de Função, selecione todos os serviços de função e clique em Avançar para continuar.

6. Na página Confirmar, reveja suas seleções e clique em Instalar.

7. Na página Progresso da instalação, confirme que a instalação foi bem-sucedida, e clique em Fechar.

### **Construindo Websites**

Para fins ilustrativos, assumimos que o novo site, chamado site10.com fará parte do domínio e servirá conteúdo html estático em todas as interfaces de rede do servidor através da porta TCP 80. Também assumimos que as páginas html já estão armazenados em um diretório que criamos chamado site10, e o diretório padrão do IIS 8 é %systemdrive%\inetpub. Observe o procedimento realizado a seguir e descubra como criar o diretório e página html.

1. Utilizando o Explorador de Arquivos, acesse em Computador C:\inetpub

2. Crie uma nova pasta chamada site10

3. Crie um novo arquivo do tipo html, com o seguinte conteúdo.

`1.` `<html>` `2.` `<body>` `3.` `<h1> Conteúdo do site 10 </h1>` `4.` `</body>` `5.` `</html>`

4. Salve como index.html

Para criar novas páginas web para o site10 utilizando o Gerenciador de IIS, faça o seguinte:

1. Expanda Servidor, e em seguida, expanda o nó Sites no painel Conexões.

2. Clique com o botão direito do mouse no item Default Web Site e em seguida clique em Adicionar Diretório Virtual, como mostrado na Figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260045/15026.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260045/15026.png)

Figura 2: Adicionar Diretório Virtual

3. Na janela Adicionar Diretório Virtual, digite o nome do site (Alias) e em Caminho físico, escolha a pasta que contém o arquivo index.html. Neste caso, o nome é site10 e o caminho é C:\inetpub\site10, como mostrado na Figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260048/15027.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260048/15027.PNG)

Figura 3: Propriedades do Diretório Virtual

4. Clique em OK na caixa de diálogo Adicionar Diretório Virtual.

O novo diretório virtual deve aparecer na lista de diretórios virtuais no painel de detalhes do Gerenciador do IIS. Sendo assim, podemos gerenciar as propriedades do novo diretório virtual e permissões.

Agora que criamos um diretório virtual que aponta para a pasta que contém a página index.htm, devemos testar o novo ambiente, navegando na página. Sem sair Gerenciador do IIS, podemos fazer um dos seguintes procedimentos:

- Botão direito do mouse o novo diretório virtual no painel Conexões, selecione Gerenciar Virtual Directory, e clique em Procurar.
- Clique no novo diretório virtual na lista Gerenciar Diretório Virtual, na caixa Ações situada no lado direito da janela.

O navegador Internet Explorer irá iniciar apresentando a página index.htm, como exibido na Figura 5.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260050/15028.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260050/15028.PNG)

Figura 4: Página sendo exibida no navegador

### **Integrando FTP em IIS 8 Páginas da Web**

Atualmente com o uso do OneDrive e Dropbox, e tudo mais sendo orientado a nuvem, podemos pensar que o FTP tornou-se uma coisa do passado. Porém ainda podemos manter e utilizar um modo simples para transferência de arquivos. A Microsoft aprimorou FTP de forma a deixa-lo mais versátil do que sua versão anterior e deu-lhe novas ferramentas de segurança que ajudarão a proteger o acesso aos dados e de transporte, mantendo a experiência de usuário simplificada e fácil. Por exemplo, FTP agora suporta restrições para acessar tentativas, bem como a integração com quota de disco do Windows Server 2012 e consequentemente melhorar o gerenciamento de armazenamento.

### **Adicionando FTP a um site IIS 8**

Uma das vantagens do serviço de publicação FTP é que podemos adicionar funcionalidade FTP para um site já existente no IIS 8. No painel Ações no console do Gerenciador do IIS, clique no link Adicionar Publicações FTP para criar o FTP, como exibido na Figura 6.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260054/15029.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260054/15029.png)

Figura 5: Adicionar Publicação FTP

Uma forma de verificar o funcionamento do servidor FTP é digitando o seguinte endereço na barra de endereço do navegador Internet Explorer, como mostrador na Figura 7.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260058/15030.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/0/260058/15030.png)

Figura 6: Acesso via FTP

Observe que o conteúdo exibido é o mesmo da pasta C:\inetpub\site10 e a partir desse momento podemos realizar o download dos arquivos existentes nesse diretório.