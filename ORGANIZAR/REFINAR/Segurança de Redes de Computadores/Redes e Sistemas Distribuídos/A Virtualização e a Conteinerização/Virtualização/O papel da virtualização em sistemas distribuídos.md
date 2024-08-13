[![](https://ampli-images.s3.amazonaws.com/production/3d0312cd-0a42-4edb-b9d9-53300f29893d/original)](https://ampli-images.s3.amazonaws.com/production/3d0312cd-0a42-4edb-b9d9-53300f29893d/original)

Dois tipos de virtualização são muito úteis no contexto de sistemas distribuídos, conforme Coulouris et al. (2013):

- Virtualização de redes;
- Virtualização de sistemas.

Esses autores observam, muito adequadamente, que a vantagem da criação e da utilização de redes virtuais advém do fato de que uma rede virtual específica para um determinado tipo de aplicação pode ser criada sobre uma rede física real, de forma que a virtual possa ser otimizada para aquela aplicação em particular, sem a necessidade de alterar as características da rede física.

______

**📝****Exemplificando**

Imagine que você está desenvolvendo um sistema distribuído de um serviço de streaming de vídeo que, obviamente, é composto por vários elementos, como banco de dados, servidor web, servidor de e-mail, servidor de autenticação etc. Suponha que o arquiteto de sistemas da empresa tenha optado por utilizar dois bancos de dados diferentes, um para armazenar informações gerais, como dados dos assinantes, datas de vencimento de assinaturas etc., do tipo SQL, e outro para armazenar os vídeos em si, com características mais adequadas para otimizar a troca de informações, do tipo NoSQL. Esses dois bancos de dados não precisam (e, por questões de segurança, nem devem) saber da existência um do outro. Para atingir esse objetivo, tipicamente as empresas criam duas redes virtuais dedicadas, de forma que, além de estarem isoladas entre si, podem ser otimizadas de acordo com a natureza do banco de dados, prevalecendo a comunicação de segmentos UDP para o banco de dados NoSQL, por exemplo, em detrimento dos segmentos TCP.

______

Para Coulouris _et a_l. (2013), a virtualização de sistemas é uma alternativa interessante por permitir emular o hardware de uma máquina física, permitindo, assim, que várias máquinas virtuais, cada uma com um sistema operacional, coexistam e se comuniquem. Os autores ainda salientam que a principal vantagem da virtualização de sistemas está no fato de que as aplicações já escritas e validadas, que dependem de um sistema operacional em específico e que necessitam se comunicar e interagir com outra aplicação em um sistema operacional diferente, podem assim fazê-lo, através da virtualização dos sistemas operacionais, sem a necessidade de que a aplicação seja reescrita ou recompilada.

______

**💭Reflita**

Pense na seguinte situação: na empresa em que você trabalha, o sistema de planejamento de recursos, conhecido simplesmente por ERP (do inglês _Enterprise Resource Planning_), utiliza um módulo de controle de estoque escrito pelo próprio time de desenvolvedores da companhia, na linguagem Asp.NET que, por sua vez, utiliza funcionalidades específicas da plataforma Windows, não sendo 100% compatível com alternativas como o .NET Core (recentemente aberto para a comunidade). Para economizar nos gastos e, principalmente, aumentar a disponibilidade do sistema ERP utilizado pelos colaboradores da empresa, suas filiais e seus representantes comerciais, o Diretor Executivo, ou CEO (do inglês _Chief Executive Officer_), decide migrar para uma solução em nuvem, de algum provedor de _cloud computin_g de mercado. Por questões financeiras, o Diretor de TI, ou CIO (do inglês _Chief Information Officer_), opta por utilizar um Sistema Operacional GNU/Linux. Como fazer para adaptar o módulo de controle de estoque? Reescrever o código seria uma opção, mas os desenvolvedores que fizeram esse módulo já não trabalham mais na empresa, e o código é muito extenso e complexo, o que significa que sua reescrita impactaria em um aumento significativo de tempo até que o “novo” ERP esteja disponível. Qual seria sua solução para esse problema?

______

Se você já utilizou ou leu a respeito de computação em nuvem, deve saber que, independentemente do tipo de serviço que você contrata e do provedor desse serviço, você já estará utilizando a virtualização em algum nível, e esses serviços são tipicamente categorizados como _IaaS_ (do inglês _Infrastructure as a Service_), PaaS (do inglês, Platform as a Service) e SaaS (do inglês, Software as a Service). Para entender melhor essa ideia, veja a figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/9788e2ed-cf01-48b2-bd64-2ac6b666859d/original)](https://ampli-images.s3.amazonaws.com/production/9788e2ed-cf01-48b2-bd64-2ac6b666859d/original)

Serviços em nuvem e níveis de virtualização. Fonte: elaborada pelo autor.

### **Arquitetura de virtualização**

A maioria das pessoas, quando ouve falar de virtualização, pensa em um sistema operacional “dentro” de um software como, por exemplo, o VirtualBox da Oracle, instalado em uma máquina física obviamente com um sistema operacional instalado. Partindo desse contexto, podemos destacar algumas características: esse sistema operacional instalado “dentro” da máquina física refere-se a uma máquina virtual, pois é similar à sua máquina física, porém, puramente emulada via software. O software que permite emular uma máquina física é, de maneira genérica, chamado de _hypervisor_ e é responsável por desacoplar a máquina física da virtual, bem como alocar os recursos da máquina física, de acordo com a necessidade da máquina virtual, conforme artigo da VMWare, uma das empresas mais conhecidas na área de virtualização (VMWARE, [s.d.]).

______

**📝****Exemplificando**

Exemplos populares de _hypervisors_ são o VMWare Player, da VMWare e o VirtualBox, da Oracle. Existem várias outras opções de _hypervisors_ disponíveis no mercado, não tão populares, mas ainda assim bastante utilizadas, como o caso do QEMU (abreviação para _Quick Emulator_), que é o _hypervisor_ utilizado pelo Android Studio (IDE oficial da Google para desenvolvimento de aplicativos Android), para emular o sistema operacional Android e poder testar os aplicativos em máquinas físicas com sistemas operacionais MS-Windows, GNU/Linux e macOS, conforme artigo do portal de desenvolvedores da Google: _Start the emulator from the command line_ (ANDROID, 2019).

______

Podemos instalar várias máquinas virtuais em uma única máquina física, limitando-se, é claro, às capacidades de processamento, RAM e armazenamento da máquina física. As máquinas físicas são tipicamente chamadas de hosts (hospedeiros), e as máquinas virtuais são tipicamente chamadas de _guests_ (convidados), embora não seja tão comum a utilização dos nomes traduzidos para o nosso idioma. A figura a seguir ilustra esses elementos.

[![](https://ampli-images.s3.amazonaws.com/production/d04a5779-adeb-4368-8620-bfc733534f8e/original)](https://ampli-images.s3.amazonaws.com/production/d04a5779-adeb-4368-8620-bfc733534f8e/original)

Elementos de máquinas virtuais. Fonte: elaborada pelo autor.

______

**⭐****Dica**

Você pode fixar seu conhecimento acessando a documentação do VirtualBox, que auxilia em todo processo de manipulação da ferramenta, assim como fornece informações sobre a tecnologia de virtualização.

Oracle® VM VirtualBox®. User Manual (ORACLE, 2018)