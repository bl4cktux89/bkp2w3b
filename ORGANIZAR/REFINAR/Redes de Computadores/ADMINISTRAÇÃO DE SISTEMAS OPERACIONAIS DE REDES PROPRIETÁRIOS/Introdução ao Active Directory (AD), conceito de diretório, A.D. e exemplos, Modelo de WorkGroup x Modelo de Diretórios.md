### **Introdução**

O Serviço de Domínio do Active Directory (AD DS) e seus serviços relacionados formam a base para as redes corporativas que executam sistemas operacionais Windows. Segundo a Microsoft (2012), o banco de dados do AD DS é o repositório central de todos os objetos do domínio, como contas de usuário, contas de computador e grupos. Esta aula aborda conceitos sobre o serviço de diretório disponível no Windows Server 2012 bem como sua estrutura e objetos relacionados.

### **Conceitos sobre AD DS**

O banco de dados existente do AD DS armazena informações sobre a identidade de usuário, contas de computadores, grupos, serviços e recursos. Os controladores de domínio também hospedam o serviço que autentica contas de usuário e computador quando eles fazem logon no domínio. Como o AD DS armazena informações sobre todos os objetos do domínio, e todos os usuários e computadores devem se conectar aos controladores de domínio ao entrar na rede, concluímos que o AD DS é o principal meio pelo qual podemos configurar e gerenciar contas de usuário e computador na rede.

### **Arquitetura lógica do Active Directory**

A camada lógica do Active Directory determina como as informações são visualizadas e mantidas no banco de dados. Além de controlar o acesso a essas informações, a camada lógica faz isso definindo os espaços de nomes (_**namespaces**_) e os esquemas de nomes (_**naming schemes**_) usados para acessar recursos armazenados no diretório. Isso fornece uma maneira consistente para acessar informações armazenadas diretório independentemente de seu tipo. Por exemplo, é possível obter informações sobre um recurso (impressora) armazenado no diretório da mesma forma que se pode obter informações sobre um usuário.

Para entender melhor a arquitetura lógica do Active Directory, é necessário conhecer os seguintes tópicos, previstos e distribuídos nessa e nas duas próximas aulas:

- Objetos do Active Directory
- Domínios do Active Directory, Árvores e Florestas
- Relação de confianças do Active Directory

Começaremos conhecendo os objetos do Active Directory.

### **Objetos do Active Directory**

Com existência de diversos tipos de recursos que podem ser armazenados no diretório, é necessário um mecanismo de armazenamento padrão, e os desenvolvedores da Microsoft decidiram usar o modelo Lightweight Directory Access Protocol (LDAP) para a organização desses dados. Neste modelo, cada recurso que se deseja representar no diretório é criado como um objeto, e seus atributos definem as informações armazenar sobre o próprio recurso. Por exemplo, o objeto conta de usuário no Active Directory tem atributos para o nome do usuário, sobrenome e nome de logon.

Um objeto que contém outros objetos é referido como um objeto contêineres e um objeto que não pode conter outros objetos é um objeto folha. Cada objeto criado dentro do diretório é classificado como de um tipo ou classe particular. As classes são objeto definido no esquema e incluem os seguintes tipos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/7/266770/13820.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/7/266770/13820.jpg)

Figura 1: Objetos do AD DS.

Quando se cria um objeto no diretório, deve-se cumprir com as regras definidas pelo esquema (_**scheme**_) para essa classe de objeto. Não só as regras do esquema ditam os atributos disponíveis para uma classe de objeto, como também determinam quais atributos são obrigatórios e quais atributos são opcionais. Quando se cria um objeto, deve-se definir atributos obrigatórios. Por exemplo, não é possível criar um objeto conta de usuário sem especificar o nome completo do usuário e nome de logon, isso porque, esses atributos são obrigatórios.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/7/266766/13821.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/7/266766/13821.jpg)

Figura 2: Conta de usuário

Algumas regras para atributos são definidas, por exemplo, a política de segurança padrão para senha, especifica que uma conta de usuário deve ter uma senha e deve atender a certos requisitos de complexidade. Se você tentar criar uma conta de usuários em uma senha ou com uma senha que não atenda aos requisitos de complexidade, a criação da conta irá falhar por causa da política de segurança.

### **Conhecendo as estruturas de domínio**

O Active Directory fornece ambas as estruturas lógica e física para componentes de rede.

As estruturas lógicas ajudam a organizar objetos de diretório, gerenciar contas de rede e recursos compartilhados. A seguir observamos alguns dos tipos de estruturas lógicas existentes no Active Directory.

- **Unidades Organizacionais**: São contêineres do AD DS e podem ser utilizadas para organizar os objetos de domínios, que muitas vezes refletem a estrutura de negócios da organização.
- **Esquema:** Define a lista de tipos e atributos que todos os objetos do AD DS possuem.
- **Domínios**: Um grupo de computadores que compartilham um banco de dados diretório comum.
- **Árvores de domínio**: Um ou mais domínios que compartilham um espaço para nome contíguo.
- **Florestas de domínio**:Uma ou mais árvores de domínio que compartilham informações de diretório comum.

Estruturas físicas servem para facilitar a comunicação de rede e definir limites físicos aos recursos de rede. Elas também ajudam a mapear a estrutura da rede física incluem o seguinte:

- **Sub-redes**: Um grupo da rede com um intervalo de endereços IP e rede máscara específica.
- **Sites**: Uma ou mais sub-redes. Sites são usados para configurar o acesso ao diretório e replicação.

### **Entendendo domínios do AD DS**

Um domínio do AD DS é um agrupamento lógico de objetos tais como contas de usuário, contas de computador e grupo, utilizados com o propósito de gerenciamento e segurança. Todos esses objetos são armazenados no banco de dados do AD DS, e uma cópia desse banco de dados é armazenada em cada controlador de domínio no domínio do AD DS.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/7/266768/13822.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/7/266768/13822.jpg)

Figura 3: Domínio do AD DS

Existem vários tipos de objetos que podem ser armazenados no banco de dados do AD DS, inclusive contas de usuário. Segundo a Microsoft (2012) as contas de usuário oferecem um mecanismo que pode ser utilizado usar para autenticar e, em seguida, autorizar os usuários a acessar recursos na rede. Cada computador incluído no domínio também deve ter uma conta no AD DS. Isso permite que os administradores de domínios usem políticas que são definidas no domínio para gerenciar os computadores. O domínio também armazena grupos, que são utilizados para agrupar objetos de segurança, como por exemplo, contas de usuário e contas de computador.

### **Associação ao domínio**

Quando um servidor faz parte de um domínio, consideramos que ele um membro de um domínio, em vez de um membro de um grupo de trabalho (workgroup). Podemos associar um computador a um domínio após sua instalação e para isso, uma conta de computador deverá ser criada no domínio usando um usuário com direitos de Administrador ou de Operador de Conta. Uma conta de computador é semelhante a uma conta de usuário e reside no banco de dados do Serviços de Domínio Active Directory que é mantido por controladores de domínio.

Se um servidor é um membro de um domínio, os usuários com associações de domínio (contas de usuário) ou permissões podem acessar o servidor e seus recursos com base nos seus direitos individuais e permissões. Isso significa que os usuários podem fazer logon no domínio e trabalhar com recursos para os quais eles têm permissões de acesso. Em contraste, se um servidor for um membro de um grupo de trabalho (workgroup), os usuários devem fazer logon a cada vez que quiserem trabalhar com um servidor e seus recursos.