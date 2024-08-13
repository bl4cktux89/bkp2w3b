### **Introdução**

O objeto usuário muitas vezes referido como conta de usuário, contém um subconjunto de atributos de um objeto, como por exemplo nome de usuário, senha e o identificador de segurança (SID). Objetos usuário do Active Directory incluem inúmeros atributos que estão indiretamente relacionados com a conta, como o endereço de e-mail, número de telefone, departamento etc., ou são atributos de uma pessoa (funcionário) representa pela conta. Nessa aula iremos aprender a criar e configurar contas de usuário no domínio.

Quando um usuário usa seu nome de usuário e senha para acessar o domínio, o serviço de diretório realiza a autenticação através do processo de logon, onde a identidade do usuário é validada comparando nome e senha de logon do usuário. Em seguida, uma vez que o usuário fez o logon, o SID da conta é comparado com as permissões em recursos e caso estejam corretos, o acesso é permitido.

Uma conta de usuário de domínio é criada e armazenada no Active Directory e permite logon em qualquer computador que faça parte do domínio e também acessar os recursos disponíveis em todo o domínio. Evidente que antes o processo de logon deve ser realizado de forma correta.

### **Criando e configurando contas de usuário de domínio**

As contas de usuário podem ser criadas pelos membros do grupo Administradores, Operadores de contas, Administradores de empresa ou grupo de administradores de domínio, através da ferramenta Usuários e Computadores Active Directory.

Siga estes passos para criar uma conta de usuário através da ferramenta Usuários e Computadores do Active Directory:

1. Clique com o botão direito na OU no qual você deseja criar o usuário, aponte para Novo e clique em Usuário.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265239/14139.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265239/14139.png)

Figura 1: Criando uma conta de usuário

2. Em Nome, digite o nome do usuário.

3. Em Iniciais, digite o as iniciais do nome do usuário.

4. Em Sobrenome, digite o sobrenome do usuário.

5. O campo Nome completo é preenchido automaticamente.

6. Em nome de logon do usuário, digite o nome que o usuário utilizara como logon.

7. Em nome de logon do usuário caixa (pré-Windows 2000), digite o nome de logon anterior ao Windows 2000, chamado frequentemente o nome de logon "de nível inferior". No banco de dados do Active Directory, o nome para este atributo é sAMAccountName.

8. Clique em Avançar.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265240/14141.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265240/14141.PNG)

Figura 2: Nova conta de usuário

9. Digite uma senha inicial para o usuário em Senha e Confirmar senha caixas. Observe que há complexidade nesse campo.

10. Selecione usuário deve alterar a senha no próximo logon. Recomenda-se sempre que você selecione essa opção para que o usuário pode criar uma nova senha desconhecido para a equipe de TI.

11. Clique em Avançar.

12. Revise o resumo e clique em Concluir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265241/14144.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265241/14144.PNG)

Figura 3: Definição da senha e opções da conta de usuário.

### **Verificando as propriedades da conta de usuário**

Um objeto conta de usuário no Active Directory, oferece a possibilidade de configurar suas propriedades adicionais. Para visualizar ou modificar esses atributos de um objeto de usuário, clique com o botão direito do mouse no nome do usuário e, em seguida, clique em Propriedades.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265242/14148.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265242/14148.png)

Figura 3: Propriedades da conta de usuário.

Atributos de um objeto de usuário está distribuído em várias categorias, como as que aparecem nas guias da caixa de diálogo propriedade. Vamos observar algumas.

- Atributos da conta: A guia conta. Essas propriedades incluem nomes de logon, senhas. Muitos desses atributos pode ser configurado quando criamos um novo usuário usando a ferramenta Usuários e Computadores do Active Directory.
- Dados pessoais: A guia Geral. Essas propriedades incluem endereço, telefone e Organização. A guia Geral expõe as propriedades de nome que estão configurados quando você cria um objeto de usuário, bem como a descrição e informações de contato de base.
- Gerenciamento de configuração do Usuário: A guia Perfil. Nessa guia podemos configurar o caminho do perfil do usuário, script de logon e pasta base.
- Participação em grupo: O guia Membro de. Nessa guia pode adicionar o usuário e remover o usuário de grupos e alterar o grupo primário do usuário.
- Serviços de terminal: O perfil dos serviços de terminal, Meio-ambiente, controle remoto, e guias sessões. Estas quatro guias permitem configurar e gerenciar a experiência do usuário quando o usuário está conectado a uma sessão do Terminal Services.
- Acesso remoto: A guia Dial-in. Podemos ativar e configurar a permissão de acesso remoto para um usuário na guia Dial-in.
- Aplicações: A guia COM +. Essa guia permite atribuir ao usuário um conjunto de partições COM +. Este recurso facilita o gerenciamento de aplicações distribuídas.

### **Definição de configuração de política de conta**

Políticas de conta protegem as contas e os dados da sua organização, reduzindo a ameaça de ataques que tentam adivinhar o nome de usuário e a senha da conta. Segundo a Microsoft (MICROSOFT, 2012), proteger seu ambiente de rede exige que todos os usuários utilizem senhas fortes. Desse modo, as configurações de política de senha devem ser utilizadas para controlar a complexidade e o tempo de vida das senhas de usuário.

### **Políticas de Conta**

Componentes de política de conta incluem políticas de senha, políticas de bloqueio de conta e a Política Kerberos.

As configurações de políticas de conta são implementadas no nível do domínio. Um domínio do Windows Server 2012 pode ter várias políticas de bloqueio de contas e senhas, que são chamadas de políticas de senha refinadas. Como por exemplo, as políticas de senha listadas na tabela a seguir.

|Política|Função|
|---|---|
|[[A senha deve satisfazer a requisitos de complexidade]]|Exige que as senhas:  <br>•  <br>Respeitem o requisito de comprimento estabelecido pelo Comprimento Mínimo da Senha, com um mínimo de três caracteres se o Comprimento Mínimo da Senha for definido como 0.  <br>•  <br>Contenham uma combinação de pelo menos três dos seguintes tipos de caracteres: letras maiúsculas, letras minúsculas, números e símbolos (sinais de pontuação).  <br>•  <br>Não devem conter o nome de usuário ou o nome de tela do usuário.|
|[[Impor histórico de senha]]|Impede que os usuários criem uma nova senha igual à senha atual ou a uma senha usada recentemente.  <br>  <br>Para especificar quantas senhas são memorizadas, forneça um valor. Por exemplo, um valor de 1 significa que apenas a última senha será memorizada, enquanto um valor de 5 significa que as cinco senhas anteriores serão memorizadas.|
|[[Tempo de vida mínimo da senha]]|Define o número mínimo de dias que devem passar antes que uma senha possa ser alterada.|
|[[Comprimento mínimo da senha]]|Especifica o menor número de caracteres que uma senha pode ter.|