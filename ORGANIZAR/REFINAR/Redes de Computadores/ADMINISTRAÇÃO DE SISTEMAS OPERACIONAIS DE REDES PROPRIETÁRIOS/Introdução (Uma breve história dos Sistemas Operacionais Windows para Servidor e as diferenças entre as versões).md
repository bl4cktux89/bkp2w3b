### **Introdução**

Esta aula aborda os conceitos relacionados ao sistema operacional para servidores Windows Server 2012 e como decidir sobre a escolha da edição que melhor atenderá as necessidades de uma organização.

O Windows Server 2012 oferece uma inovadora interface ao usuário, com novas ferramentas de gerenciamento, maior o suporte ao Windows PowerShell, e centenas de novas funcionalidades nas áreas de rede, armazenamento e virtualização (MICROSOFT, 2012). Ele também foi projetado para a computação em nuvem e para que as empresas possam aproveitar os benefícios oferecidos por essa tecnologia, ele fornece uma base para a construção de ambas as soluções de nuvens públicas e privadas.

Windows Server 2012 é um sistema operacional disponível somente na arquitetura 64 bits e as suas edições suportam as mesmas características e ferramentas de administração, sendo assim, é possível usar as técnicas apresentadas nas aulas, independentemente de qual edição do Windows Server esteja sendo usada.

### **Funcionalidades desempenhadas por um servidor**

Especialista na área de tecnologia afirmam que a previsão é de que a computação em nuvem se torne um aspecto importante do futuro das empresas. Porém nem todos os serviços e aplicações estão armazenados pela tecnologia de computação em nuvens e diante disso, os servidores locais utilizados atualmente por essas organizações em suas redes formam o esquema central da rede e desempenham funcionalidades e oferecem, segundo a Microsoft (2012), os seguintes recursos para os computadores clientes:

- Serviços de infraestrutura: Esses serviços permitem que os clientes se conectem e comuniquem com outros recursos na rede, sendo assim, esses servidores fornecem recursos de infraestrutura para os clientes, entre eles estão disponíveis o serviço DNS (Sistema de Nomes de Domínio) e de protocolo DHCP (Protocolo de Configuração Dinâmica de Host.
- Arquivos e impressoras compartilhados: Servidores fornecem um local centralizado que permite aos usuários armazenar e compartilhar documentos. Eles também hospedam recursos, como impressoras compartilhadas, que permitem que grupos de usuários otimizem recursos de maneira mais eficiente.
- Acesso à rede. Servidores fornecem recursos de autenticação e autorização a clientes na rede. Ao se autenticarem em um servidor, um usuário e um cliente podem provar sua identidade.
- Implantação de aplicativos: Servidores são implantados localmente para auxiliarem na implantação de aplicativos, atualizações e sistemas operacionais em clientes na rede organizacional.

Embora o Windows Server 2012 esteja pronto para integração com a computação em nuvem, ele também é ainda altamente adequado para as tarefas tradicionais que os sistemas operacionais Windows Server têm executado ao longo da história. Portanto, é possível configurar e implantar o Windows Server 2012 para realizar as mesmas cargas de trabalho, ou semelhantes, configuradas para servidores que executam versões anteriores ao Windows Server 2012.

**EDIÇÕES DO WINDOWS SERVER 2012**

Antes de implantar o Windows Server 2012, é necessário compreender como cada uma das edições pode trazer benefícios para as tarefas relacionadas as funções dos servidores da sua organização.

Entre as diferentes edições disponíveis do Windows Server 2012, a escolha correta permite que as organizações se adequarem de acordo com suas necessidades, evitando assim pagar por recursos que não precisam usar.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/4/2/254252/10404.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/4/2/254252/10404.jpg)

Figura 1:Windows Server 2012 Editions. Disponível em: http://blogs.technet.com/b/ieitpro/archive/2012/10/08/windows-server-2012-editions.aspx

A tabela a seguir lista as edições do Windows Server 2012.

|Edição|Descrição|
|---|---|
|[[O sistema operacional Windows Server 2012 Standard]]|Fornece todas as funções e recursos disponíveis na plataforma do Windows Server 2012. Dá suporte para até 64 soquetes e até 4 TB de RAM. Inclui duas licenças de máquina virtual.|
|[[O sistema operacional Windows Server 2012 Datacenter]]|Fornece todas as funções e recursos que estão disponíveis na plataforma do Windows Server 2012. Inclui licenças ilimitadas de máquina virtual para máquinas virtuais que são executadas no mesmo hardware. Dá suporte para 64 soquetes, até 640 núcleos de processador e até 4 TB de RAM.|
|[[O sistema operacional Windows Server 2012 Foundation]]|Projetado para proprietários de pequenas empresas, permite apenas 15 usuários, não pode ser ingressado em domínio e inclui funções de servidor limitadas. Dá suporte a um núcleo de processador e até 32 GB de RAM.|
|[[O sistema operacional Windows Server 2012 Essentials]]|Próxima edição do Small Business Server. Deve ser o server raiz em um domínio. Não pode funcionar como um servidor Hyper-V, Server Core, de Clustering de Failover ou de Serviços de Área de Trabalho Remota. Tem limites para 25 usuários e 50 dispositivos. Dá suporte para dois núcleos de processador e 64 GB de RAM.|
|[[Microsoft Hyper-V Server 2012]]|Plataforma Hyper-V autônoma para máquinas virtuais sem interface do usuário. Nenhum custo de licenciamento (gratuito) para o sistema operacional host, mas as máquinas virtuais são licenciadas normalmente. Dá suporte para 64 soquetes e 4 TB de RAM. Compatível com ingresso em domínio. Não dá suporte para outras funções do Windows Server 2012 além de recursos limitados de serviços de arquivo.|
|[[O sistema operacional Windows Storage Server 2012 Workgroup]]|Dispositivo de armazenamento unificado para iniciantes. Limitado a 50 usuários, um núcleo de processador, 32 GB de RAM. Compatível com ingresso em domínio.|
|[[O sistema operacional Windows Storage Server 2012 Standard]]|Dá suporte para 64 soquetes, mas é licenciado com base em incrementos de dois soquetes. Dá suporte para 4 TB de RAM. Inclui duas licenças de máquina virtual. Compatível com ingresso em domínio. Dá suporte para algumas funções, incluindo as funções de Servidor DHCP e DNS, mas não para outras, como o AD DS (Serviços de Domínio do Active Directory), AD|
|[[O sistema operacional Windows MultiPoint Server 2012 Standard]]|Dá suporte para vários usuários que acessam o mesmo computador host diretamente usando mouses, teclados e monitores separados. Limitado a um soquete, 32 GB de RAM e um máximo de 12 sessões. Dá suporte para algumas funções, incluindo as funções de Servidor DHCP e DNS, mas não para outras, como o AD DS, o AD CS e o AD FS. Não dá suporte para ingresso em domínio.|
|[[O sistema operacional Windows MultiPoint Server 2012 Premium]]|Dá suporte para vários usuários que acessam o mesmo computador host diretamente usando mouses, teclados e monitores separados. Limitado a dois soquetes, 4 TB de RAM e um máximo de 22 sessões. Dá suporte para algumas funções, incluindo as funções de Servidor DHCP e DNS, mas não para outras, como o AD DS, o AD CS e o AD FS. Compatível com ingresso em domínio.|

  
  

Diante das opções e escolhas referentes as edições do Windows Server 2012, os administradores de sistemas podem fazer uma economia substancial selecionando a edição apropriada de acordo com as necessidades e a função desempenhada pelo servidor da organização.