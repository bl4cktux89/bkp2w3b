[![](https://ampli-images.s3.amazonaws.com/production/a3b709a5-6eed-405a-a976-d80fe6516ff9/original)](https://ampli-images.s3.amazonaws.com/production/a3b709a5-6eed-405a-a976-d80fe6516ff9/original)

O termo computação em nuvem (do inglês, _cloud computing_) se refere a uma tecnologia que possibilita acessar recursos e serviços via internet, sem a necessidade de instalações de softwares em seu computador. Dessa forma, é permitido que os usuários façam acessos por meio de qualquer dispositivo, seja ele um computador ou telefone celular.

______

**📝****Exemplificando**

Um exemplo de utilização de serviços em nuvem é quando você edita um trabalho da universidade utilizando o Google Docs e esse trabalho fica armazenado na nuvem. Outro exemplo é quando você escuta uma música no Spotify, ou até mesmo assiste a um filme no Netflix. Todas essas situações trazem um contato com a computação em nuvem. Elas têm em comum o fato de não exigirem nenhuma instalação nem consumirem recursos do seu dispositivo, todas são serviços on-line. Para acessá-los, só precisamos de um navegador e ter conexão com a internet.

______

A figura abaixo ilustra múltiplos dispositivos acessando a nuvem, a qual contém diversos tipos de dados.

[![](https://ampli-images.s3.amazonaws.com/production/e28db9ff-e5d6-488e-a8ee-865df760e9c9/original)](https://ampli-images.s3.amazonaws.com/production/e28db9ff-e5d6-488e-a8ee-865df760e9c9/original)

Cloud computing. Fonte: Shutterstock.

**O papel da virtualização em sistemas distribuídos**

Dois tipos de virtualização são muito úteis no contexto de sistemas distribuídos, conforme Coulouris _et al_. (2013):

- Virtualização de redes.
- Virtualização de sistemas.

Os autores observam, muito adequadamente, que a vantagem da criação e utilização de redes virtuais advém do fato de que uma rede virtual específica para um determinado tipo de aplicação pode ser criada sobre uma rede física real, de forma que a rede virtual possa ser otimizada para aquela aplicação em particular, sem a necessidade de alterar as características da rede física.

_______

**📝****Exemplificando**

Imagine que você está desenvolvendo um sistema distribuído de um serviço de _streaming_ de vídeo que, obviamente, é composto por vários elementos, como banco de dados, servidor web, servidor de e-mail, servidor de autenticação, etc. Supondo que o arquiteto de sistemas da empresa optou por utilizar dois bancos de dados diferentes: um para armazenar informações gerais, como dados dos assinantes, datas de vencimento de assinaturas, etc., do tipo SQL; e outro para armazenar os vídeos em si, com características mais adequadas para otimizar a troca de informações, do tipo NoSQL. Esses dois bancos de dados não precisam (e, por questões de segurança, nem devem) saber da existência um do outro. Para atingir esse objetivo, tipicamente as empresas criam duas redes virtuais dedicadas, de forma que, além de estarem isoladas entre si, podem ser otimizadas de acordo com a natureza do banco de dados, prevalecendo a comunicação de segmentos UDP para o banco de dados NoSQL, por exemplo, em detrimento aos segmentos TCP.

_______

Para Coulouris et al. (2013), a virtualização de sistemas é uma alternativa interessante por permitir emular o hardware de uma máquina física, permitindo que várias máquinas virtuais, cada uma com um sistema operacional, possam coexistir e se comunicar. Os autores ainda salientam que a principal vantagem da virtualização de sistemas está no fato de que aplicações já escritas e validadas, as quais dependem de um sistema operacional em específico, que necessitam se comunicar e interagir com outra aplicação em um sistema operacional diferente, podem assim fazê-lo através da virtualização dos sistemas operacionais, sem a necessidade de que a aplicação seja reescrita novamente ou recompilada.

_______

**💭Reflita**

Pense na seguinte situação: na empresa que você trabalha, o sistema de planejamento de recursos, conhecido simplesmente por ERP (do inglês, _Enterprise Resource Planning_), utiliza um módulo de controle de estoque escrito pelo próprio time de desenvolvedores de sua empresa, na linguagem Asp.NET, que, por sua vez, utiliza funcionalidades específicas da plataforma Windows, não sendo 100% compatível com alternativas, como o .NET Core (recentemente aberto para a comunidade). Para economizar os gastos e, principalmente, aumentar a disponibilidade do sistema ERP utilizado pelos colaboradores da empresa, suas filiais e seus representantes comerciais, o Diretor Executivo, ou CEO (do inglês, _Chief Executive Officer_), decide migrar para uma solução em nuvem, de algum provedor de _cloud computing_ de mercado. Por questões financeiras, o Diretor de TI, ou CIO (do inglês, _Chief Information Officer_), opta por utilizar um sistema operacional GNU/Linux. Como fazer para adaptar o módulo de controle de estoque? Reescrever o código seria uma opção, mas os desenvolvedores que fizeram esse módulo já não trabalham mais na empresa, e o código é muito extenso e complexo, o que significa que sua reescrita impactaria em um aumento significativo de tempo até que o “novo” ERP esteja disponível. Qual seria sua solução para esse problema?

_______

Se você já utilizou ou leu a respeito de computação em nuvem, deve saber que, independentemente do tipo de serviço que você contrata e do provedor desse serviço, você já estará utilizando a virtualização em algum nível. Esses serviços são tipicamente categorizados como IaaS (do inglês, _Infrastructure as a Service_), PaaS (do inglês, _Platform as a Service_) e SaaS (do inglês, _Software as a Service_). Para entender melhor essa ideia, veja figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/da347bbe-8105-4a53-8435-af2a82979910/original)](https://ampli-images.s3.amazonaws.com/production/da347bbe-8105-4a53-8435-af2a82979910/original)

Serviços em nuvem e níveis de virtualização. Fonte: elaborada pelo autor.