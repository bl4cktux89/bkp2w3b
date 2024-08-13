### **Introdução**

O Windows Internet Naming Service (WINS) fornece um banco de dados centralizado para registrar de forma dinâmica mapeamentos de nomes NetBIOS em uma rede IPv4. Atualmente na maioria das redes ele é mantido com o propósito de dar suporte e compatibilidade à aplicativos legados e também para as primeiras versões do Microsoft Windows, como por exemplo Windows 98, que utilizam WINS para resolução de nomes.

Para novas configurações de redes, onde não existem computadores com sistemas operacionais legados, não haverá necessidade de utilizar WINS. Nessas situações somente o DNS é necessário para o realizar o processo de resolução de nome.

### **Conceitos sobre WINS**

O WINS é um protocolo cliente/servidor e todos os servidores Windows podem ser utilizados para mantém e fornecer esse serviço a computadores clientes na rede. Todos os computadores Windows têm um cliente WINS que é instalado automaticamente e as configurações que são definidas servem para especificar em quais servidores o serviço estará disponível. O acesso aos recursos, tais como compartilhamentos, devem ser encontrados utilizando nomes de NetBIOS.

Observe que na guia WINS em Configurações avançadas do protocolo TCP/IP é possível especificar o endereço do servidor WINS e configurações adicionais para o computador cliente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258500/13528.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258500/13528.png)

Figura 1: Guia de configurações WINS em um computador cliente.

### **Espaço de nomes NetBIOS e registro de nome**

A arquitetura WINS é muito diferente da existente no DNS. Ao contrário do DNS o WINS tem um espaço de nomes de forma plana e não usa uma hierarquia. Cada computador ou recurso em uma rede Windows tem um nome NetBIOS, que pode conter até 15 caracteres. Esse nome deve ser exclusivo na rede e nenhum outro computador ou recurso pode ter o mesmo nome.

O WINS mantém e atualiza automaticamente um banco de dados com mapeamentos de nomes para endereço IP. Sempre que um computador ou recurso fica disponível na rede, ele se registra com o servidor WINS e informa o nome e endereço IP que está usando. Contanto que nenhum outro computador ou recurso da rede esteja utilizando esse nome, o servidor WINS aceita a solicitação e registra o computador ou recurso em seu banco de dados. O registro de nome não é permanente, isso porque, cada nome que está registrado tem um período de locação.

### **Configuração do servidor WINS**

Para fazer com que o servidor com o Windows Server tenha a função WINS, é necessário instalar o serviço. Este serviço não requer um servidor dedicado e usa recursos mínimos na maioria dos casos. Isto significa que é possível instalar o serviço WINS em um servidor que contenha outras funcionalidades, tais como servidor DNS, servidor DHCP ou controlador de domínio. O único requisito fundamental é que o serviço WINS seja instalado em um computador com um endereço IPv4 estático.

### **Instalando o serviço WINS**

1. No Gerenciador de Servidor, selecione Adicionar Funções e Recursos no menu Gerenciar. Isso inicia o assistente Adicionar funções e recursos. Se o assistente exibe a página Antes de começar, leia o texto introdutório e, em seguida, clique em Avançar.

2. Na página Tipo de instalação ou instalação baseado em recurso é selecionado por padrão baseada em função. Clique em Avançar.

3. Na página Seleção de Servidor, é possível optar por instalar funções e recursos em servidores que executam ou discos rígidos virtuais ou selecione um servidor do pool de servidores. Quando estiver pronto para continuar, clique em Avançar duas vezes.

4. Na página Recursos, selecione Servidor WINS e clique em Avançar. Se forem necessários recursos adicionais, aparecerá uma caixa de diálogo adicional. Clique em Adicionar Recursos para fechar a caixa de diálogo e adicionar os recursos necessários para a instalação do servidor. Quando estiver pronto para continuar, clique em Avançar.

5. Clique em Instalar e quando o assistente terminar de instalar os recursos selecionados, clique em Fechar.

Depois de instalar o Servidor WINS, o console WINS está disponível no menu Ferramentas no Gerenciador de Servidores. Quando abrir o console do WINS, selecione o servidor WINS disponível e visualize suas entradas, como mostrado na Figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258501/14125.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258501/14125.PNG)

Figura 2: Console do WINS