### **Introdução**

Monitorar um servidor não é algo tão trivial como podemos imaginar. No entanto, precisamos definir um plano claro, com um conjunto de objetivos que esperamos alcançar. Nessa aula vamos conhecer as razões pela qual precisamos monitorar um servidor e as ferramentas que você pode usar para fazer isso. Posteriormente conheceremos o Firewall do Windows.

### **Por que monitorar o servidor?**

Solucionar problemas de desempenho do servidor é uma das principais razões para o monitoramento. Por exemplo, os usuários podem estar tendo problemas para se conectar ao servidor, sendo assim, podemos monitorar o servidor para solucionar esses problemas. Mas antes disso, o objetivo é rastrear o problema usando os recursos de monitoramento disponíveis e posteriormente resolvê-lo.

Outro motivo comum para querer monitorar um servidor é melhorar o desempenho do servidor. Você faz isso através da melhoria disco, reduzindo o uso de CPU, e reduzindo a carga de tráfego de rede no servidor. Por exemplo, quando o número de usuários que acessam um servidor cresce, podemos não ser capaz de reduzir a carga de tráfego de rede, mas podemos melhorar o desempenho do servidor por meio de balanceamento de carga ou através da distribuição de arquivos em unidades separadas.

### **Preparando-se para monitorar**

Antes de iniciar o monitoramento de um servidor, devemos estabelecer métricas base de desempenho para o servidor. Para fazer isso, medimos o desempenho do servidor em vários momentos e em diferentes condições de trabalho. Desse modo, podemos comparar os resultados desses desempenhos e determinar como o servidor se comporta nesses momentos diferentes.

Depois de estabelecer métricas base, devemos formular um plano de monitoramento abrangendo as seguintes etapas:

1. Determinar quais os eventos do servidor devem ser monitorados.

2. Definir os filtros para reduzir a quantidade de informações coletadas.

3. Configurar os contadores de desempenho para medir o uso de recursos.

4. Determinar os dados do evento para que ele possa ser analisado.

5. Analisar os dados do evento para ajudar a encontrar soluções para os problemas.

### **Usando Ferramentas de Monitoramento**

As ferramentas apresentadas são Desempenho do Sistema em Ferramentas de Monitoramento, Conjunto de Coletores de Dados e Relatórios, que mantem relatórios de confiabilidade do sistema.

O Monitor de desempenho é legado, podemos acessá-lo clicando com o botão direito do mouse em Ferramentas de Monitoramento, como mostrado na Figura 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259246/eventos-1.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259246/eventos-1.PNG)

Monitor de recursos

Fonte: Figura 1: Monitor de recursos

### **Desempenho do Sistema**

A ferramenta Desempenho do Sistema usa objetos e contadores e fornecer o monitoramento em tempo real de seus sistemas. Uma explicação de cada um consiste em:

- Objetos: Os objetos do Desempenho do Sistema são recursos específicos que podem ser medidos. Alguns objetos que são comumente medidos são processador, memória, interface de rede e disco físico.
- Contadores: Os Contadores são as métricas individuais dentro de um objeto. Por exemplo, o objeto Processor inclui contadores, tais como % tempo do processador, % Tempo de usuário.

### **Monitor de recursos**

O Monitor de recursos funciona constantemente e captura os contadores sobre os quatro principais recursos do seu sistema. Podemos acessá-lo clicando com o botão direito do mouse em Ferramentas de Monitoramento e selecionando a opção Monitor de recursos.

A Figura 2 mostra o Monitor de recursos com a guia Visão Geral selecionada. O painel esquerdo mostra detalhes sobre cada um dos recursos e o painel da direita mostra um gráfico de cada um dos recursos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259241/form_obj_0.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259241/form_obj_0.PNG)

Figura 2: Monitor de recursos

Onde podemos selecionar qualquer um dos quatro recursos através de sua guia e visualizar os detalhes adicionais sobre o desempenho do processador, memória, disco ou interface de rede. Um dos benefícios do Monitor de recursos é a capacidade de filtrar os resultados de acordo com processos ou serviços específicos. Por exemplo, para identificar a carga que um aplicativo específico está colocando em seu sistema, podemos selecionar apenas os processos do aplicativo em questão.

### **Firewall do Windows**

O firewall do Windows ajuda a proteger um computador contra ataques por usuários não autorizados. Windows Server 2012 inclui um firewall básico chamado Firewall do Windows e um firewall avançado chamado Firewall do Windows com Segurança Avançada.

### **Informações iniciais sobre o firewall**

Os firewalls inspecionam o conteúdo existente nos pacotes recebidos e os comparam juntamente a um conjunto de regras existentes. No entanto, se as regras autorizarem o pacote, o firewall o transmitirá ao protocolo TCP/IP para posterior processamento, caso contrário, não autoriza o pacote, e o firewall o descartará e, se o log estiver habilitado, criará uma entrada em seu arquivo de log.

A lista de tráfego permitido é preenchida de uma das seguintes maneiras:

- Quando o computador que tem o firewall habilitado inicia a comunicação, o firewall cria uma entrada na lista de forma que a resposta seja permitida.
- Um administrador de sistemas configura as exceções no firewall. Sendo assim, o acesso será permitido a determinados programas executados em seu computador ou acesso a portas de conexão especificadas do computador.

Escolher a estratégia para que o firewall trabalhe de forma adequada é uma tarefa complexa, levando em consideração qual porta deverá ficar aberta ou fechada. Quando elaboramos uma estratégia para o firewall de uma organização, é importante considerar todas as regras e opções de configuração disponíveis.

### **Configurações padrão do firewall**

A etapa inicial para o planejamento da configuração do firewall é determinar o status atual do firewall em relação ao sistema operacional. A opção Firewall do Windows no Painel de Controle permite configurar opções básicas. Como as apresentadas as seguir:

- Ativar ou desativar o item Firewall do Windows no Painel de Controle
- Habilitar e desabilitar regras
- Conceder exceções para portas e programas
- Definir algumas restrições de escopo

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259242/15013.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259242/15013.PNG)

Figura 3: Firewall do Windows

Como exibido na Figura 3, o Firewall do Windows existente no Painel de Controle é mais apropriado para usuários que não têm experiência em configuração de firewall e que estão configurando opções básicas do firewall.

### **Configurações usando o Firewall do Windows no Painel de Controle**

Podemos adicionar exceções ao firewall a fim de restringir a abertura de uma porta a conexões de entrada de computadores específicos ou de uma sub-rede local. É recomendável criar essa restrição no escopo da abertura de porta para reduzir o nível de exposição do computador a usuários mal-intencionados.

Utilizando o Firewall do Windows no Painel de Controle, como exibido na Figura 4, podemos alterar o escopo para uma exceção do firewall.

1. No item Firewall do Windows do Painel de Controle, selecione na lista a direita a opção Permitir um aplicativo ou recurso do através do Firewall do Windows

2. Em seguida selecione na lista o aplicativo e recursos permitidos. Observe que podemos escolher ainda o escopo da aplicação, marcando a opção para Domínio, Privado ou Público.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259243/form_obj_0%20(1).PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259243/form_obj_0%20(1).PNG)

Figura 4: Configuração do Firewall do Windows

### **Firewall do Windows com Segurança Avançada**

O Firewall do Windows com Segurança Avançada permite definir configurações de firewall mais avançadas. Através desse console, encontramos a maioria das opções de firewall de um jeito fácil de usar, além de todos os perfis de firewall. Para acessar o Firewall do Windows com Segurança Avançada, utilize a opção Ferramentas existente no Gerenciador de Servidor, como mostrado na Figura 5.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259244/form_obj_0.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259244/form_obj_0.PNG)

Figura 5: Acesso ao Firewall do Windows com Segurança Avançada

O Firewall do Windows com Segurança Avançada permite e oferece suporte a perfis separados, utilizando as definições de firewall e as regras de segurança de conexão computadores membros ou não de um domínio. Além de oferecer suporte a regras mais detalhadas, inclui a filtragem com base em usuários e grupos no Active Directory, endereços IP de origem e destino, número de porta IP, configurações de ICMP, configurações de IPsec, tipos específicos de interfaces e outros serviços.

O Firewall do Windows com Segurança Avançada, exibido na Figura 6, geralmente está atrelado as diretivas de segurança, permitindo diversos métodos para proteger computadores nas redes internas e todos os componentes da rede contra ataques mal-intencionados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259245/15017.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259245/15017.PNG)

Figura 6: Console do Firewall do Windows com Segurança Avançada

### **Utilizando o Firewall do Windows com Segurança Avançada**

As configurações avançadas de firewall são criadas e definidas através do console do Firewall do Windows com Segurança Avançada. Esse console contém um assistente de regras e permite escolher as configurações adicionais que não estão disponíveis no Firewall do Windows do Painel de Controle.

Essas configurações incluem:

- Configurações de criptografia
- Restrições de serviços
- Restrição de conexões de computadores por nome
- Restrição de conexões para usuários ou perfis específicos
- Percurso de borda que permita que o tráfego ignore os roteadores de conversão de endereço de rede (NAT)
- Configuração de regras de saída
- Configuração de regras de segurança
- Exigência de IPsec para conexões de entrada

### **Utilizando o assistente de Nova Regra para criar uma nova regra**

1. Outra forma de executar o firewall é, clicar em Executar e digitar _**wf.msc**_ em seguida clique em OK.

2. No painel esquerdo do Firewall do Windows com Segurança Avançada, clique com o botão direito do mouse em Regras de Entrada e clique em Nova Regra.

3. Complete o Assistente de Nova Regra de Entrada usando as configurações desejadas.