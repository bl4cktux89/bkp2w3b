### **Introdução**

Com o Windows Server 2012, a Microsoft traz sua experiência na construção e operação de nuvens públicas para o sistema operacional de servidor, ajudando a torná-lo uma plataforma dinâmica e altamente disponível e de custo eficaz para nuvens privadas. O Windows Server 2012 oferece às empresas e provedores de hospedagem uma base para uma infraestrutura de nuvem escalável e dinâmica.

Esta aula define o cenário para a introdução do Windows Server 2012 e ainda por que a computação em nuvem está se tornando uma solução cada vez mais popular para o negócio e necessidades de TI.

### **O que é computação em nuvem?**

Computação em nuvem é uma descrição geral que engloba várias tecnologias diferentes e que segundo o National Institute of Standards and Technology (NIST) define que:

“A computação em nuvem é um modelo de habilitação de acesso à rede conveniente e sob demanda para um pool de recursos de computação configuráveis compartilhados (por exemplo, redes, servidores, armazenamento, aplicativos e serviços) que pode ser rapidamente provisionado e liberado como um esforço mínimo de gerenciamento ou interação do provedor de serviço.”

De acordo com as definições da Microsoft (2012), as formas mais comuns para oferecimento de modelos para computação em nuvem são:

- Plataforma como serviço (PaaS): Esta abordagem envolve o uso da nuvem para fornecer serviços de execução para aplicativos tais como armazenamento e integração de aplicativos que foram projetados para uma estrutura pré-especificada em relação a arquitetura baseada em nuvem. Ao usar PaaS, o administrador de sistemas pode desenvolver aplicativos baseados em nuvem personalizados para o seu negócio e, em seguida, hospedá-los na nuvem para que os usuários possam acessá-los em qualquer lugar através da Internet. PaaS também pode ser usado para criar aplicativos _multi-tenant_, onde vários usuários podem acessa-lo simultaneamente. SQL Azure da Microsoft é um exemplo de uma oferta de PaaS, que permite que as empresas de provisionem e implantem bancos de dados SQL para a nuvem sem a necessidade de implementação e manutenção de uma infraestrutura de servidor locais.
- Infraestrutura como serviço (IaaS): Esta abordagem envolve a criação de pools de computação, armazenamento e recursos de conectividade de rede que podem então ser entregues aos clientes como serviços baseados em nuvem que são faturados por seu uso. IaaS constitui a base para SaaS e PaaS, proporcionando um ambiente virtualizado padronizado, flexível e que normalmente se apresenta para o cliente como cargas de trabalho de servidores virtualizados. No modelo IaaS, o cliente pode personalizar totalmente os recursos necessários de processamento, armazenamento e rede e com o sistema operacional e os aplicativos que o negócio exige. Ao usar a abordagem IaaS, o cliente está livre da necessidade de adquirir e instalar hardware para atender novas cargas de trabalho. A tecnologia Hyper-V da plataforma Windows Server, junto com a família de produtos System Center, representa a oferta da Microsoft no modelo IaaS.
- Software como um serviço (SaaS): Esta abordagem envolve o uso da nuvem para entregar um único pedido para vários usuários, independentemente de sua localização ou o tipo de dispositivo que estão usando. SaaS contrasta com a abordagem mais tradicional de implantar instâncias separadas de aplicativos para dispositivos de computação de cada usuário. As vantagens do modelo SaaS estão relacionadas a forma a qual os aplicativos podem ser gerenciados a partir de uma única localização central, proporcionando assim, redução de custos e sobrecarga de gerenciamento. SaaS normalmente é usado para entregar aplicativos baseados em nuvem que têm suporte mínimo para personalização, tais como e-mail, software de produtividade. O Office 365 da Microsoft é um exemplo de uma oferta de SaaS, ele fornece acesso seguro aos usuários independendo do lugar. A lógica por trás da computação em nuvem está em conceder acesso aos e-mails, calendários compartilhados, mensagens instantâneas (IM), videoconferência e ferramentas para colaboração de documentos.

### **Requisitos técnicos para o sucesso utilizando a computação em nuvem**

Se você está pensando em mudar o seu negócio para a nuvem e busca sucesso na implementação, é importante estar ciente dos componentes de uma plataforma de nuvem. A Figura 1 ilustra os três modelos de serviço padrão para implementação de soluções de nuvem privada e pública.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/4/252495/11657.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/4/252495/11657.jpg)

Figura 1: Os três modelos de serviço padronizados para a nuvem.

A hierarquia do diagrama apresentado na figura anterior ilustra que tanto IaaS e PaaS podem ser usados como a base para a construção de SaaS. Na abordagem IaaS, é possível construir toda a arquitetura em nesse modelo, por exemplo, utilizando servidores web com balanceamento de carga para o front-end e servidores em cluster para o seu negócio). Na verdade, a única diferença entre IaaS e um datacenter tradicional é que os aplicativos estão rodando em servidores que são virtuais, em vez de físicos.

### **Nuvens públicas e privadas**

Uma nuvem pública é um serviço de nuvem hospedado por um provedor de serviços de nuvem e disponibilizado para uso público, nela pode-se hospedar um único locatário ou locatários de várias organizações. Assim sendo, a segurança de nuvem pública não é tão forte quanto a segurança de nuvem privada, mas, em geral, a hospedagem em nuvem pública tem custo menor, pois esses custos são absorvidos por vários locatários.

Em contraste, nuvens privadas são a infraestrutura de nuvem dedicada a uma única organização. Nuvens privadas podem ser hospedadas pela própria organização ou por um provedor de serviços de nuvem garantindo que esses serviços não sejam compartilhados com nenhuma outra organização.

Nuvens privadas são muito mais que implantações de hipervisor em grande escala. Elas permitem o uso do pacote de gerenciamento do Microsoft System Center 2012, o qual torna possível fornecer a distribuição via autoatendimento de serviços e aplicativos. Uma organização, por exemplo, que possui sua própria nuvem privada, possibilitaria que seus usuários utilizassem um portal de autoatendimento para solicitar aplicativos multicamadas, incluindo componentes de armazenamento, servidor Web e servidor de banco de dados. O Windows Server 2012 e os componentes do pacote do System Center 2012 são configurados para processar automaticamente uma solicitação de serviço, sem exigir a implantação manual de máquinas virtuais e softwares de servidor de banco de dados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/6/265647/15525.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/6/265647/15525.png)

Figura: Núvem privada e pública

### **Métodos de instalação**

A Microsoft distribui o Windows Server 2012 em uma mídia óptica ou em formato de imagem .iso (ISO). O formato ISO está se tornando mais comum à medida que as organizações adquirem softwares via Internet em vez de obterem a mídia removível física.

Após conseguir obter o Windows Server 2012 da Microsoft, será possível utilizar um método para implantar esse sistema operacional. Entre os métodos disponíveis para instalar o sistema operacional Windows Server 2012, é possível optar por:

- Mídia Óptica
- Mídia USB
- Imagem ISO Montada
- Compartilhamento de Rede
- Windows DS
- System Center Configuration Manager

### **Tipos de instalação**

A forma de implantar o Windows Server 2012 em um servidor específico depende das circunstâncias dessa instalação. A instalação em um servidor que esteja executando o Windows Server 2008 R2 requer diferentes ações do que a instalação em um servidor que esteja executando uma edição x86 do Windows Server 2003.

Ao fazer uma instalação do sistema operacional Windows Server 2012, é possível escolher uma das opções na tabela a seguir.

![[Screenshot_from_2022-03-31_00-39-52.png]]

Ao fazer uma nova instalação, você pode implantar o Windows Server 2012 em um disco não particionado ou em um volume existente.

### **A plataforma de virtualização**

A virtualização pode trazer muitos benefícios para as empresas, incluindo o aumento da agilidade, maior flexibilidade e melhor eficiência relacionadas aos custos. Combinando a virtualização com a infraestrutura e as ferramentas necessárias para os aplicativos e serviços em nuvem é possível oferecer ainda mais benefícios para as organizações que precisam se adaptar e escalar a sua infraestrutura e consequentemente atender as novas exigências do ambiente de negócios. Com suas inúmeras melhorias apresentadas pelo Hyper-V, o Windows Server 2012 fornece a base para a construção de nuvens privadas e pode oferecer os benefícios da computação em nuvem para as mais diversas organizações.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/9/265943/15526.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/9/265943/15526.png)