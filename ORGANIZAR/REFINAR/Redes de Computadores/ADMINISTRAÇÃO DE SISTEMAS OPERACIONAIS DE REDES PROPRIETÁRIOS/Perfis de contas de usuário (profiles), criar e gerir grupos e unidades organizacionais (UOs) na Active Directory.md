### **Introdução**

O gerenciamento de contas de usuários é uma das suas principais tarefas desenvolvidas por administrador Microsoft Windows. Um objeto conta de usuário no Serviço de Domínio do Active Directory (AD DS) tem suas propriedades relacionadas à identidade de segurança, ou à conta, do usuário. Ela fornece a base da identidade e do acesso no AD DS. Portanto, processos consistentes, eficientes e seguros relativos à administração das contas de usuário são a base do gerenciamento da segurança corporativa.

Nessa aula entenderemos a importância do objeto conta de usuários e como mantê-la organizada em uma Unidade Organizacional.

### **Diferenças entre contas de usuário e contas de grupo**

O Windows Server 2012 fornece contas de usuário e contas de grupo (do qual os usuários podem ser um membro). As contas de usuário são projetadas para os indivíduos e as contas do grupo são projetadas para tornar a administração de vários usuários mais fácil.  Contas de grupo são geralmente conhecidas simplesmente como grupos.

Com contas de usuário, podemos permitir que os usuários individuais para fazer logon na rede e acessem os recursos disponíveis. Com a utilização de grupo, podemos gerenciar recursos para múltiplos usuários e definir permissões e privilégios atribuídos a contas de usuário ou grupo determinar quais ações os usuários podem executar, bem como quais recursos podem acessar.

### **Contas de usuário**

Dois tipos de contas de usuário são definidos no Windows Server:

- As contas de usuário definidas no Active Directory são chamadas de contas de usuário de domínio. Através dessas contas de usuário de domínio é possível acessar recursos de todo o domínio.
- As contas de usuário definidas em um computador local são chamadas de contas de usuários locais. Contas de usuários locais têm acesso a apenas o computador local.

### **Nome de usuário (login) e senhas.**

Todas as contas de usuários são identificadas com um nome de usuário, também conhecidas como login.

### **Identificadores de segurança e contas de usuário**

Embora os nomes de usuários descrevem privilégios e permissões, os identificadores chave para as contas de usuário são conhecidos como Identificadores de Segurança (Security Identifiers, SID). Os SID são identificadores exclusivos que são gerados quando criarmos novas contas.

O Windows Server usa esses identificadores para associar contas de usuário de forma independente. Os SID servem a muitos propósitos, como por exemplo, ao mudarmos (renomearmos) um nome de usuário o Windows Server mapeia um SID específico para um novo nome. Porém quando excluímos uma conta e depois disso, criamos uma conta com o mesmo nome de usuário, a nova conta não terá os mesmos privilégios e permissões que o anterior, isso porque a nova conta terá um novo SID.

### **Adicionando uma conta de usuário**

Podemos criar contas de usuário de domínio através da ferramenta Usuários e Computadores do Active Directory seguidos os passos:

1. Clique com o botão direito do mouse na unidade organizacional em que deseja colocar a conta de usuário, clique em Novo e, em seguida, clique em Usuário. Isso abre o Assistente Novo Objeto - Usuário, mostrado na Figura 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/5/272598/01.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/5/272598/01.PNG)

Figura 1: Novo objeto conta de usuário

2. Como mostrado na Figura 1, a primeira página do assistente permite configurar o nome de exibição do usuário e logon nome. Digite o nome do usuário em primeiro lugar, inicial do meio, e último nome nas caixas de texto fornecidas. Esses campos são usados para criar o nome completo, o que é o nome de exibição do usuário. Clique em Avançar.

3. Defina a senha do usuário, como mostrado na Figura 2. Lembre-se que essa senha, por padrão, deve contém complexidade.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/6/272600/02.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/6/272600/02.PNG)

Figura 2: Definição da senha do usuário.

As opções para esta página são as seguintes:

- O usuário deve alterar senha no próximo logon: Selecionado, o usuário deve alterar a quando efetuar o primeiro acesso.
- O usuário não pode alterar a senha: Se selecionado, o usuário não pode alterar a senha.
- Senha nunca expira: Se selecionado, a senha para esta conta nunca expira, ou seja, não haverá pedido de mudança de senha. Esta definição substitui a diretiva de conta de domínio.
- Conta desativada: Se selecionado, a conta estará desativada e consequentemente não poderá ser usado.

6. Clique em Avançar e, em seguida, clique em Concluir para criar a conta

### **Grupos**

Além de contas de usuário, o Windows Server permite criar e gerenciar grupos, que de um modo geral, é utilizado para simplificar o gerenciamento, uma vez que podemos agrupar contas de usuário com algo em comum, por exemplo, contas de usuário de um determinado setor de uma organização e posteriormente conceder permissões para esses usuários. Se um usuário é membro de um grupo e pode acessar um recurso, como uma impressora, outros usuários que fazem parte desse mesmo grupo, também podem acessar o mesmo recurso. Assim, podemos dar a um usuário acesso a vários recursos relacionados com suas tarefas, apenas fazendo com que esses usuários sejam membros do grupo.

### **Tipos de grupo**

Em uma rede corporativa baseada no Windows Server 2012, há dois tipos de grupo: segurança e distribuição.

Ao definir um grupo, devemos escolher o seu o tipo e o escopo. Os tipos existentes são segurança e distribuição.

- Os grupos de distribuição, são usados principalmente por aplicativos de e-mail. Como exemplo, o envio de uma mensagem a um grupo de distribuição faz com que ela seja enviada a todos os membros do grupo.
- Os grupos de segurança são entidades de segurança com SIDs e portanto, esses grupos são utilizados para controlar a segurança do acesso aos recursos.

### **Escopos de grupo**

O escopo de um grupo determina sua visibilidade e as associações existentes. Segundo a Microsoft (MICROSOFT, 2013) existem quatro escopos de grupo:

- Local. Esse tipo de grupo é destinado a servidores ou estações de trabalho autônomas, em servidores membro de domínio que não são controladores de domínio ou em estações de trabalho membro de domínio.
- Domínio Local. Esse tipo de grupo é principalmente usado para gerenciar o acesso aos recursos ou para atribuir responsabilidades (direitos) de gerenciamento (direitos).
- Global. Esse tipo de grupo é principalmente usado para consolidar usuários com características semelhantes. Por exemplo, os grupos globais são geralmente usados para consolidar os usuários que fazem parte de um departamento ou de um local geográfico.
- Universal. Esse tipo de grupo é muito útil em redes de vários domínios, pois combina as características dos grupos de domínios locais e dos grupos globais.

### **Adicionando um grupo**

Podemos criar grupos globais através da ferramenta Usuários e Computadores do Active Directory. Desse modo, para criar um grupo global, siga estes passos:

1. Inicie o Usuários e Computadores do Active Directory e clique com o botão direito do mouse na Unidade Organizacional em que deseja colocar o grupo, clique em Novo e, em seguida, clique em grupo. Isso abre a caixa de diálogo Novo Objeto - Grupo, mostrado na Figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/6/272602/03.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/6/272602/03.PNG)

Figura 3: Novo grupo

2. Digite um nome para o grupo

3. Selecione um escopo de grupo (Domain Local, Global ou Universal).

4. Selecione um tipo de grupo (Segurança ou Distribuição).

5. Clique em OK para criar o grupo. Depois de criar a conta, você pode adicionar membros e definir propriedades adicionais.

### **Unidade Organizacional**

Uma unidade organizacional (UO) é um objeto do tipo contêiner dentro de um domínio que pode ser utilizado para consolidar ou organizar objetos como usuários, grupos, computadores e outros. Geralmente refletem a estrutura funcional ou de negócios de uma organização. Por exemplo, podemos criar UOs nomeando-as como RH, TI, Engenharia e Marketing para o domínio empresa.br, onde os respectivos objetos (contas de usuário, computadores e grupos) de cada um desses departamento seria mantido.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/6/272603/04.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/6/272603/04.PNG)

Figura 3: Unidades Organizacionais.