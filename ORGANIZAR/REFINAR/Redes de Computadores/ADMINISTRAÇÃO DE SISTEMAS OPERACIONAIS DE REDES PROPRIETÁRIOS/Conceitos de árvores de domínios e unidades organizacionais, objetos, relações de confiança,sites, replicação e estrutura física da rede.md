### **Introdução**

O Serviços de Domínio do Active Directory (AD DS) e seus serviços relacionados formam a base para as redes corporativas que executam sistemas operacionais Windows. Segundo a Microsoft (2012), o banco de dados do AD DS é o repositório central de todos os objetos do domínio, como contas de usuário, contas de computador e grupos. Na aula anterior abordamos os conceitos sobre o serviço de diretório e seus objetos, dando continuidade ao assunto, nesta aula abordaremos os conceitos sobre os componentes disponíveis na estrutura do AD DS.

### **Entendendo Floresta e Árvores de domínio**

Cada domínio do Active Directory tem um nome de domínio DNS, como **empresa.br**. Um ou mais domínios que compartilham os mesmos dados de diretório são referidos como uma floresta. Os nomes de domínio dentro desta floresta podem ser formados de maneira não contíguo ou contíguo de acordo com a hierarquia de nomes DNS.

Quando os domínios têm uma estrutura de nomes contíguo, eles estão na mesma árvore de domínio. A Figura 1 mostra um exemplo de uma árvore de domínio. Neste exemplo, o domínio raiz **empresa.br** tem dois domínios filho: **sp.empresa.br** e **rj.empresa.br**. Estes domínios, por sua vez podem têm subdomínios. Todos os domínios são parte da mesma árvore, porque eles têm o mesmo domínio raiz.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265244/13836.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265244/13836.jpg)

Figura 1: Uma árvore de domínio.

Se os domínios em uma floresta têm nomes DNS não contíguos, então eles formam árvores de domínio separadas dentro da floresta. Como mostra a Figura 2, uma floresta de domínio pode ter um ou mais domínios árvores. Neste exemplo, os domínios **empresa.br**e **matriz.br** formam as raízes de árvores de domínio separadas na mesma floresta.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265245/13837.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265245/13837.jpg)

Figura 2: Uma floresta de domínio.

### **Entendendo as unidades organizacionais**

Uma unidade organizacional (UO) é um objeto do tipo contêiner dentro de um domínio que pode ser utilizado para consolidar ou organizar objetos como usuários, grupos, computadores e outros. Geralmente refletem a estrutura funcional ou de negócios de uma organização. Por exemplo, podemos criar UOs nomeando-as como RH, TI, Engenharia e Marketing para o domínio empresa.br, onde os respectivos objetos (contas de usuário, computadores e grupos) de cada um desses departamento seria mantido.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265252/13948.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265252/13948.PNG)

Figura 3: Utilizando a console Usuários e Computadores do Active Directory para gerenciar usuários, grupos, computadores e unidades organizacionais.

### **Relação de Confiança**

Na aula anterior, consideramos que um computador poderia ser configurado para trabalhar em um grupo de trabalho. Porém percebemos que uma máquina quando ingressa em um domínio, a autoridade de segurança local do sistema começa a confiar nos serviços de armazenamento de identidade e autenticação fornecidos pelo domínio. Isso permite que uma conta de usuário armazenado no domínio seja autenticada, e posteriormente possa ser definido acesso a recursos no servidor.

O mesmo conceito pode ser utilizado a outros domínios, isso porque, um domínio pode autenticar os usuários de outro domínio e também pode permitir que os usuários acessem recursos atribuídos no domínio. Isto é feito através do estabelecimento de uma relação de confiança de domínio. Em uma relação de confiança, o domínio confiante estende seu domínio de confiança para que ele confie nos serviços de armazenamento de identidade e autenticação do domínio confiante. As contas de usuário no domínio confiante podem ser autenticadas, e as SID (Identificação Segura) de contas de usuário no domínio confiável podem ser adicionadas ao domínio confiante. Dentro de uma floresta, cada domínio confia em todos os outros domínios.

Sempre que implementando um cenário que envolve dois ou mais domínios AD DS, é provável que trabalharemos com relações de confiança.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265249/13838.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/2/265249/13838.jpg)

Figura 4: Relação de confiança entre domínios

A figura 4 mostra uma relação de confiança simples, onde o domínio A confia no domínio B. Isso faz com que o domínio A seja o domínio confiante e domínio B o domínio confiável. Se um usuário no domínio B conectar-se ou faz logon em um computador no domínio A, o domínio A passará o pedido de autenticação para um controlador de domínio no domínio B. O domínio A também pode usar as identidades de domínio B - usuários e grupos, por exemplo direitos de usuário concessão - e definir acesso a recursos no domínio A.

### **Sites**

Quando consideramos a topologia da rede de uma organização de forma distribuída, provavelmente encontraremos e discutiremos sobre os sites da rede. Sites no Active Directory, além de criar um limite de replicação, tem um significado muito específico, pois se trata de um objeto que representa uma parte da empresa em que a conectividade de rede e considerada boa, isso porque, os controladores de domínio dentro de um site replicam as alterações dentro de segundos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/4/7/274780/13840.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/4/7/274780/13840.jpg)

Figura 5: Sites do Active Directory

### **Replicação**

Os serviços de replicação distribuem dados de diretório em uma rede, incluindo o próprio banco de dados, bem como os dados necessários para implementar políticas e configuração, incluindo scripts de logon. Active Directory mantém uma partição separada do armazenamento de dados chamado Configuração que mantém informações sobre a configuração de rede, topologia e serviços.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/4/7/274783/13841.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/4/7/274783/13841.jpg)

Figura 7: Replicação entre controladores de domínio