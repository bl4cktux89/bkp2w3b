A palavra heterogêneo significa: Que é de natureza diferente da dos outros componentes do complexo ou da conglomeração de que faz parte; dissimilar.... Composto de partes constituintes diferentes quanto à espécie, qualidades ou características...

(De acordo com o dicionário Michaellis (2016))

Portanto uma rede heterogênea pode apresentar diversos tipos de hardwares, protocolos ou softwares.

Grandes corporações trabalham com redes heterogêneas utilizando várias plataformas diferentes, tais como: Linux, Windows, Solaris, entre outros.

Atualmente, temos as redes virtuais que estão fisicamente conectadas e podem conectar equipamentos em diferentes localidades com sistemas semelhantes ou até mesmo diferentes.

O que dificulta as possibilidades de compartilhamento entre as redes heterogêneas e seus sistemas operacionais é o fato da existência de arquivos serem criados com estruturas diferentes, sendo que um não reconheceria o outro.

Com a possibilidade de comunicação entre as redes heterogêneas teremos um maior grau de gerenciamento no que diz respeito à autenticação de usuários, permissões, definições de cotas e compartilhamento.

Se considerarmos uma arquitetura de rede do tipo Cliente/Servidor, encontraremos no Modelo OSI a possibilidade de comunicação entre máquinas heterogêneas, implementado pelas 7 camadas do Modelo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/2/312294/22669.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/2/312294/22669.png)

Middleware

Fonte: Figura 3.7 (b) - Pag. 50 do Livro Sistemas Distribuídos ¿ Princípios e Paradigmas

Veremos um exemplo de comunicação entre redes heterogêneas apresentando os serviços oferecidos pelo DNS que possibilita a comunicação entre diversos tipos de redes de diferentes arquiteturas.

### **DNS**

O DNS (Domain Name System) é considerado um dos maiores serviços de nomeação que está em uso hoje em dia. Utilizado para consultar endereços IP de sites da Internet, servidores de correio e equipamentos em geral.

Através do DNS conseguimos resolver nomes de sites para endereços IP’s e Endereços IP’s para nomes de sites, ou seja, ele oferece um método padrão para associar nomes a endereços de Internet.

Uma curiosidade do DNS é que ele existe há algumas décadas e ainda não se cogita a hipótese de sua substituição, dada a sua funcionalidade e arquitetura simples, que atende adequadamente aos propósitos da sua criação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293100/18554.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293100/18554.jpg)

Exemplo de acesso DNS

No DNS o espaço de nomes é organizado de forma hierárquica e sua estrutura é uma raiz. O DNS utiliza rótulos para montar sua cadeia de caracteres cujo comprimento máximo é de 63 caracteres. A representação em cadeia de um nome de caminho consiste em uma listagem de seus rótulos.

Algumas das ferramentas do DNS são auxiliares na resolução dos nomes de sites, tais como: **a** **zona de pesquisa direta e a zona de pesquisa inversa.**

### **Zona de Pesquisa Direta**

É nesta configuração que fica definido o suporte à função do DNS em resolver nomes de host’s para endereços IP’s.

Nesta zona devemos configurar o serviço **WINS** que serve para resolver nomes não encontrados no DNS e a **Transferência de Zona**, que controla se a “zona” poderá ser transferida para outros servidores.

### **Zona de Pesquisa Inversa**

A Zona de Pesquisa Inversa possibilita a localização de um determinado endereço IP e deseja saber o nome do site que esteja associado a esse endereço, diferentemente do que ocorre na pesquisa direta, onde se tem um nome de site e se procura um endereço IP.

Para tratar da pesquisa inversa, foi criado um domínio de nome **in-addr.arpa**, que fornece a resolução reversa de nomes, sem a necessidade de efetuar uma pesquisa em todos os servidores DNS que estejam associados.

Na estrutura de um determinado tipo de rede, o Espaço de nome DNS define que um nó é tratado como uma entrada e deve ter um nome definido, chamado de nome de domínio, que pode ser absoluto ou relativo. Assim, o conteúdo do nó é formado por um conjunto de **Registros de Recursos**, cuja função é permitir que administradores usem vários servidores para um único domínio DNS, a fim de tratar de assuntos TCP/IP entre hosts.

Quando da configuração do registro de recurso é criado um serviço chamado **SOA** (Start of Authority – Início de Autoridade), que contém informações do nome do administrador do sistema responsável pela zona representada, ou o hospedeiro em que os dados podem ser buscados.

No espaço de nomes DNS cada uma das Zonas é implementada por um servidor de nomes que é replicado visando dar disponibilidade. Nesse recurso, as atualizações para as Zonas ocorrem devido as modificações realizadas no banco de dados do DNS local do servidor.

Os servidores secundários, quando necessitam resolver nomes, solicitam ao servidor primário que transfira seu conteúdo, uma vez que não acessam diretamente o banco de dados do DNS. Essa operação de solicitação é possibilitada pelo DNS através da Transferência de Zona.

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/6/8/326883/index.html)

### **IMPLEMENTAÇÃO HIERÁRQUICA – LDAP**

Muitos sistemas, incluindo o Active Diretory – AD, da Microsoft, se utilizam de serviços distribuídos de diretório combinando uma nomeação estruturada com uma nomeação baseada em atributos. O que possibilita a adoção dessa possibilidade é um serviço chamado **LDAP** (Lightweigt Directory Access Protocol – Protocolo leve de Acesso a Diretório).

O LDAP consiste de vários registros conhecidos como entrada de diretório, que é um registro de recurso do DNS, onde cada registro é composto por (atributo e valor), associando um tipo a cada atributo. O LDAP mantém os serviços de informação referente aos diretórios distribuído sobre uma rede que tenha como padrão o uso do IP (Internet Protocol).

Na figura abaixo podemos visualizar uma entrada simples de diretório identificando endereços de rede de alguns servidores:

|Atributo|Abreviatura|Valor|
|---|---|---|
|[[Country]]|C|NL|
|[[Locality]]|L|Amsterdam|
|[[Organization]]|O|Vrije Universiteit|
|[[OrganizationalUnit]]|OU|Comp. Sc|
|[[CommonName]]|CN|Main server|
|[[Mail_Servers]]|-|137.37.20.3, 130.37.24.6, 137.37.20.10|
|[[FTP_Server]]|-|130.37.20.20|
|[[WWW_Server]]|-|130.37.20.20|

  
  

Podemos observar na figura, o uso de uma convenção de nome descrita nos padrões LDAP, aplicado aos primeiros atributos da tabela mostrando, por exemplo, os atributos _**Locality e Country**_ fornecendo informações adicionais sobre o local onde a entrada está armazenada.

Baseado nos dados e informações citados acima, podemos concluir que sem a existência do DNS aumentaria a dificuldade de se acessar um determinado site (para isso deveria-se conhecer o IP), ou seu e-mail, ou ainda, ficar navegando pela internet a procura de informações e conhecimento.

**SAIBA MAIS SOBRE A CONSULTA DNS**

Para saber mais sobre a consulta DNS, acesse:

- https://technet.microsoft.com/pt-br/library/cc775637(v=ws.10).aspx