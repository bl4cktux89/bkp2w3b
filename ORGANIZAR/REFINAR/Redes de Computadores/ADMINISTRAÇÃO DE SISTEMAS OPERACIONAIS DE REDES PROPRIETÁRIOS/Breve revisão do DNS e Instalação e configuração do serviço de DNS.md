### **Introdução**

O DNS é um serviço de resolução de nomes que mapeia nomes de computador para endereços IP. Quando utilizamos o DNS, um nome de host totalmente qualificado, como por exemplo, **empresa.br**, pode ser resolvido para um endereço IP como 131.1.1.20, permitindo assim que os computadores em uma rede possam encontrar outros computadores. O DNS opera sobre a pilha de protocolos TCP/IP e pode ser integrado com o Windows Internet Name Service (WINS), Dynamic Host Configuration Protocol (DHCP) e ao Active Directory (AD). Nessa aula vamos conceituar, instalar e gerenciar a funcionalidade DNS.

### **Entendendo o DNS**

Para fornecer esse serviço, o DNS utiliza um banco de dados contendo informações de nomes de computadores e endereços IP. O computador cliente DNS inicia uma consultas e atualizações no banco de dados DNS. Por exemplo, dentro de uma organização, um usuário precisa localizar um servidor e para isso, utiliza o nome DNS **servidordearquivos.empresa.br**, o cliente consulta o servidor DNS afim de descobrir o nome para o endereço IP, assim que o servidor DNS retornar a endereço IP do host (servidordearquivos) o cliente poderá acessá-lo

O DNS organiza grupos de computadores em domínios através de uma estrutura hierárquica que pode ser definida com base de toda a Internet.  Os vários níveis dentro dessa hierarquia identificam computadores de forma individual, domínios organizacionais e domínios de nível superior. Como por exemplo, para o nome do host totalmente qualificado **servidor.empresa.br**, **servidor** representa o nome do host, **empresa** é o domínio organizacional e **br** é o domínio de nível superior.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/5/272591/13434.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/2/5/272591/13434.png)

Figura 1: Hierarquia do DNS

Domínios de nível superior estão na raiz da hierarquia DNS e também são chamados de domínios de raiz. Esses domínios são organizados geograficamente, por tipo de organização e por função. Domínio como **empresa.br**, também são referidos como domínio de segundo nível ou domínios pais, porque eles são os pais de uma estrutura organizacional. É possível dividir domínios pais em subdomínios, também conhecidos como domínios filho. Por exemplo, o nome de domínio totalmente qualificado (FQDN) para um computador dentro de um domínio **rh** poderia ser designado como **servidor. rh.sp.empresa.br**, onde servidor, é o nome do host, rh e sp são domínios filho, e empresa é o domínio pai.

### **Instalando e gerenciando um servidor DNS**

Para usar um serviço Servidor DNS, é necessário realizar a instalação dessa função, para isso, no Gerenciado de servidor, clique em Gerenciar e, em seguida, clique em Adicionar funções e recursos, ou selecione Adicionar funções e recursos no painel de Inicialização Rápida. Isso inicia o assistente para Adicionar funções e recursos. O assistente exibirá a página de boas-vindas Antes de começar, após leitura do texto, clique em Avançar. Na página Selecionar Funções, selecione Servidor DNS.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/1/260146/14280.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/1/260146/14280.png)

Figura 1: Assistente para adicionar função ¿ DNS

### **Zonas e registros DNS**

Uma zona DNS é parte específica do _**namespace**_ DNS e contém tipos de registros, ela é hospedada em um servidor responsável por responder a consultas de registros em um domínio específico, como por exemplo, o servidor DNS responsável por resolver o nome **www.empresa.br** para um endereço IP matem a zona **empresa.br**.

Os tipos mais usados de zonas no DNS do Windows Server são zonas de pesquisa direta e zonas de pesquisa inversa.

### **Zonas de pesquisa direta**

As zonas de pesquisa direta resolvem nomes de host para endereços IP e hospedam registros de recurso comuns, como:

- Host (A) IPv4,
- Host (AAAA) IPv6,
- Alias (CNAME),
- Serviço (SRV),
- Servidor de mensagens (MX),
- Início de autoridade (SOA) e
- Servidor de nomes (NS).

O tipo de registro mais comum é o registro de recurso de host (A).

### **Configurando Zonas de pesquisa direta**

Procedimento de configuração de uma zona de pesquisa direta em um tipo de zona primária. Para configurar uma zona de pesquisa direta em um tipo de zona primária, siga os passos a seguir.

1. Abra o console DNS.

2. No console DNS, clique com o botão direito do mouse no servidor DNS e, em seguida, clique em Nova zona.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/1/260166/14281.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/1/260166/14281.PNG)

Figura 2: Nova zona de pesquisa direta

3. Na página Bem-vindo ao Assistente de nova zona, clique em Avançar.

4. Na página Tipo de zona, verifique se a opção Zona primária está selecionada e clique em Avançar.

5. Na página Zona de pesquisa direta ou inversa, verifique se a opção Zona de pesquisa direta está selecionada e clique em Avançar.

6. Na página Nome da zona, digite o nome DNS da zona em que este servidor terá autoridade e clique em Avançar.

7. Na página Arquivo de zona, clique em Avançar para aceitar os padrões.

8. Na página Atualização dinâmica, selecione uma das opções a seguir e clique em Avançar.

a. Permitir apenas atualizações dinâmicas seguras (recomendado para o Active Directory). Esta opção só estará disponível para zonas integradas ao Active Directory.

b. Permitir atualizações dinâmicas seguras e não seguras. Esta opção não é recomendada, pois as atualizações vindas de origens não confiáveis poderão ser aceitas.

c. Não permitir atualizações dinâmicas. Esta opção requer que você atualize os registros manualmente.

9. Após concluir a página Assistente de nova zona, clique em Concluir.

10. Feche o console DNS.

### **Zonas de pesquisa inversa**

As zonas de pesquisa inversa resolvem endereços IP para nomes de domínio. As zonas de pesquisa inversa hospedam registros de recurso, como:

- Ponteiro (PTR),
- SOA e
- NS

### **Configurando Zonas de pesquisa inversa**

Procedimento de configuração de uma zona de pesquisa inversa em um tipo de zona primária. Para configurar uma zona de pesquisa inversa em um tipo de zona primária, siga os passos a seguir.

1. Abra o console DNS.

2. No console DNS, clique com o botão direito do mouse no servidor DNS e, em seguida, clique em Nova zona.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/1/260169/14283.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/1/260169/14283.png)

Figura 3: Nova zona de pesquisa inversa.

3. Na página Bem-vindo ao Assistente de nova zona, clique em Avançar.

4. Na página Tipo de zona, verifique se a opção Zona primária está selecionada e clique em Avançar.

5. Na página Zona de pesquisa direta ou inversa, selecione Zona de pesquisa inversa e clique em Avançar.

6. Na página Nome da zona de pesquisa inversa, no campo Identificação de rede, digite a parte de identificação de rede do endereço IP da zona e clique em Avançar.

7. Na página Arquivo de zona, clique em Avançar para aceitar os padrões.

8. Na página Atualização dinâmica, selecione uma das opções a seguir e clique em Avançar.

a. Permitir apenas atualizações dinâmicas seguras (recomendado para o Active Directory).

b. Permitir atualizações dinâmicas seguras e não seguras.

c. Não permitir atualizações dinâmicas.

9. Na página Concluindo o Assistente de nova zona, clique em Concluir.

10. Feche o console DNS.