### **Introdução**

As políticas de grupo simplificam a gerenciamento, dando aos administradores controle centralizado sobre privilégios, permissões, usuários e computadores. Nessa aula entendermos as vantagens de como utilizar as políticas de grupo.

### **Entendendo as políticas de grupo**

Podemos entender uma política de grupo (Group Policy, GPO) como sendo um conjunto de regras que ajudam a gerenciar usuários e computadores. Elas podem ser aplicadas em vários domínios ou em domínios individuais. As políticas de grupo estão diretamente ligadas aos objetos armazenamento no Active Directory.

Através de políticas de grupo, podemos controlar o ambiente e ainda fazer o seguinte:

- Controle o acesso aos componentes do Windows, os recursos do sistema, recursos de rede, utilitários Painel de Controle, a área de trabalho, e tela Iniciar.
- Criar diretórios gerenciados centralmente para pastas especiais, como a pasta Documentos do usuário.
- Definir scripts de usuário e de computador para executar em horários especificados.
- Configurar políticas para o bloqueio de conta e senhas, auditoria, atribuição de direitos de usuário e segurança.

### **Em que ordem são múltiplas políticas aplicadas?**

Quando várias políticas estão em vigor, as políticas são aplicadas na seguinte ordem:

1. Políticas de Grupo Local

2. Políticas grupo de sites

3. As políticas de grupo de domínio

4. Políticas de grupo da unidade organizacional

Se as definições de política entrarem em conflitos, as definições de política aplicadas por último têm precedência e substitui previamente definidas definições de política já aplicadas. Por exemplo, as políticas de unidade organizacional têm precedência sobre as políticas de grupo de domínio.

### **Quando as políticas são grupo aplicados?**

As definições de política de grupo são divididas em duas categorias:

- Aqueles que se aplicam a computadores
- Aqueles que se aplicam a usuários

As diretivas do computador são normalmente aplicadas durante a inicialização do sistema, e as políticas de usuário são normalmente aplicados durante o logon. A sequência exata dos acontecimentos é muito importante para o comportamento do sistema.

Os eventos que ocorrem durante a inicialização e logon são as seguintes:

1. A rede é iniciada e, em seguida, Windows Server aplica as políticas do computador. Por padrão, as políticas de computador são aplicadas uma de cada vez na ordem especificada.

2. Windows Server executa scripts de inicialização. Por padrão, os scripts de inicialização são executados um de cada vez e não são exibidos para o usuário, a menos que especificado.

3. Um usuário faz o logon e depois de ser validado, Windows Server carrega o seu perfil de usuário.

4. Windows Server aplica as políticas de usuário. Por padrão, as políticas de usuário são aplicadas, um por vez, na ordem especificada. A interface de usuário é exibida enquanto as políticas de usuário estão sendo processados.

5. Windows Server executa scripts de logon. Os scripts de logon da Diretiva de Grupo por padrão são executadas simultaneamente.

6. Windows Server exibe a interface shell de início configurado na política de grupo.

7. Por padrão, a Diretiva de Grupo é atualizada quando um usuário faz logoff ou quando o computador é reiniciado.

### **Console para gerenciamento de GPO**

O console principal chamado o Group Policy Management Console (GPMC), é um recurso que podemos adicionar a qualquer instalação a partir da versão do Windows Server 2008 usando o assistente Adicionar funções e recursos.

Quando editamos uma GPO no GPMC, ele abre o Editor de Política de Gestão de Grupo, que podemos usar para gerenciar as definições de política.

### **Gerenciando Políticas em domínio e Unidade Organizacional**

Quando implantamos os Serviços de Domínio Active Directory (AD DS), utilizamos o Diretiva de Grupo baseado no Active Directory. Cada domínio ou unidade organizacional pode ter uma ou mais políticas de grupo. Políticas de grupo listadas no topo de uma lista de políticas tem precedência maior do que políticas listadas abaixo nessa mesma lista. Isso garante que as políticas sejam aplicadas de forma adequada em todos os domínios e unidades organizacionais.

### **Usando o Console de Gerenciamento de Política de Grupo**

Para executar o Console de Gerenciamento de Política de Grupo **(**GPMC) a partir do menu executar digite _**gpmc.msc**_ e pressione Enter.

Como mostrado na Figura 1, o nó raiz do console é rotulado como Gerenciamento de Política de Grupo e abaixo deste nó observamos o nó Floresta. O nó Floresta representa a floresta na qual o domínio está participando

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/4/262439/14916.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/4/262439/14916.PNG)

Figura 1: Console de gerenciamento de GPO.

### **Conhecendo o Editor de Política**

Com o GPMC, podemos editar uma GPO existente, pressionando botão direito do mouse nela e, em seguida, selecionando Editar no menu de atalho. Como mostra a Figura 2, o editor de política tem dois nós principais:

- Configuração do computador: Permite definir políticas que devem ser aplicadas a computadores, independentemente de quem faz logon.
- Configuração do Usuário: Permite que definir as políticas que deverão ser aplicados aos usuários, independentemente de qual computador eles logon

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/4/262440/14917.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/4/262440/14917.PNG)

Figura 2: Editor de Gerenciamento de Política de Grupo

A partir dos nós Configuração do Computador e Configuração do Usuário, encontraremos as Políticas e nós de Preferências. Definições para as políticas gerais são listadas sob o nó Políticas. Configurações de preferências gerais são listados sob o nó Preferências.

A configuração exata relacionada a Configuração do computador ou Configuração do usuário depende de qual o tipo de política que você está criando, mesmo assim, encontramos geralmente que modelos para Configuração do Computador e Configuração do Usuário.

### **Criando e Vinculando GPOs**

Quando trabalhamos com uma GPO, criamos um objeto e vinculámos (_**link**_) a um objeto tipo contêiner específico dentro do Active Directory. Podemos criar um vínculo de uma GPO a um domínio específico, site ou UO. Pode criar e, em seguida, vincular um GPO a um site, domínio ou unidade organizacional, seguindo estes passos:

1. No Gerenciamento de Política de Grupo, expanda a o nó floresta e em seguida expanda o nó Domínios.

2. Pressione e botão direito do mouse Criar um GPO neste domínio e fornecer um link para ele aqui.., em seguida, na caixa de diálogo Novo GPO em seguida.

3. Digite um nome descritivo para o GPO, como por exemplo, GPO Workstation Seguro. Observe esses procedimentos na Figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/4/262442/14918.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/4/262442/14918.PNG)

Figura 3: Criar nova GPO

4. Clique com botão direito do mouse no novo GPO (GPO Workstation Seguro) e, em seguida, clique em Editar, como mostrado na Figura 4.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/4/262443/14919.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/4/262443/14919.PNG)

Figura 4: Editar GPO

5. No editor de política, configure as definições de política necessárias, e em seguida, feche o editor de política.

Quando criamos ou realizamos alterações em uma política, essas alterações são imediatas propagadas. Os computadores cliente solicitação nos seguintes momentos:

- Quando o computador é iniciado
- Quando um usuário fizer logon
- Quando um aplicativo ou usuário solicita uma atualização