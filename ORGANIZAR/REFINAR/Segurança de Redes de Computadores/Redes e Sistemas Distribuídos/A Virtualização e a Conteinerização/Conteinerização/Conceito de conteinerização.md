[![](https://ampli-images.s3.amazonaws.com/production/7d728723-03c6-4972-8aa9-5eec68983f5f/original)](https://ampli-images.s3.amazonaws.com/production/7d728723-03c6-4972-8aa9-5eec68983f5f/original)

Uma das tecnologias mais populares que temos atualmente é o uso de contêineres para a execução de sistemas dos mais variados tipos. Isso ocorre devido à facilidade e à flexibilidade que advêm do uso dos mesmos. O contêiner funciona como uma tecnologia que dá o suporte para o funcionamento de uma aplicação e pode ser considerado a emulação de nossa aplicação. Quando a aplicação é executada através de um contêiner, ela tem todas as bibliotecas e os elementos necessários para o funcionamento disponíveis dentro do contêiner. Uma maneira simples para entender o que são os chamados contêineres é imaginar que eles permitem a criação de ambientes virtuais isolados e independentes para serem utilizados por aplicações, similar ao resultado do uso de máquinas virtuais. Entretanto, um grande diferencial está no fato de que os contêineres são mais leves que as máquinas virtuais, por possuírem uma arquitetura mais otimizada.

______

**🔁Assimile**

O contêiner traz muitas facilidades e é considerado uma das principais tendências de TI. Sua utilização simplifica a aplicação da metodologia DevOps e facilita o desenvolvimento. Grandes empresas, como a Google, usam essa tecnologia.

______

Se fosse necessário desenvolver um sistema em linguagem C para o cadastro de produtos do estoque de uma loja de varejo, poderíamos criar um contêiner que tivesse todas as bibliotecas essenciais para o funcionamento do sistema e, assim, nossa aplicação seria virtualizada através de um contêiner, sem a necessidade de um sistema operacional, pois, neste caso, já precisaríamos de uma máquina virtual.

Conforme pode ser visto na figura a seguir, uma grande vantagem de contêineres em relação às máquinas virtuais é que não há, obrigatoriamente, a necessidade de instalar um sistema operacional completo, visto que as plataformas de conteinerização aproveitam bibliotecas compartilhadas com o sistema operacional hospedeiro. Por essa razão, os contêineres ocupam menos espaço em disco e consomem menos RAM e processamento que as máquinas virtuais e, assim, possibilita a utilização de mais contêineres em uma mesma máquina física, favorecendo o uso de uma arquitetura mais modular para as aplicações.

[![](https://ampli-images.s3.amazonaws.com/production/fce314ca-e030-4bfc-8d5f-c80be0b26d3a/original)](https://ampli-images.s3.amazonaws.com/production/fce314ca-e030-4bfc-8d5f-c80be0b26d3a/original)

Comparação das arquiteturas de máquinas virtuais versus contêineres. Fonte: elaborada pelo autor.

______

**💭Reflita**

Agora que conhecemos algumas vantagens dos contêineres em relação às máquinas virtuais, quais benefícios uma empresa que executa aplicações em máquinas virtuais poderia adquirir migrando a execução de suas aplicações para contêineres? Você acredita que seria benéfica essa migração?

______

Duas das principais características a favor da conteinerização são o baixo acoplamento entre os contêineres e a facilidade de migração entre provedores de cloud computing. Ambas se devem ao fato de que a ideia do contêiner é “empacotar” a sua aplicação em um módulo que é facilmente instalado em qualquer sistema operacional que suporte o uso de contêineres (e os principais sistemas operacionais utilizados em servidores possuem esse suporte).

No lugar do hypervisor, quando tratamos de máquinas virtuais, temos os chamados contêiner engines (por vezes chamados de contêiner daemons). Existem várias implementações para esses engines, como o Docker, o LXD, o Rkt, o Mesos e o Windows Server Containers, mas o mais popular entre eles é o Docker, sobre o qual aprenderemos na próxima aula.

Porém, para começar a ter ideia do que se trata, quando falamos do Docker, estamos na realidade falando de uma empresa – chamada Docker – que foi responsável pela popularização dos contêineres, por meio de eventos e divulgação de material técnico. Essa companhia criou sua própria implementação que, coincidentemente, é chamada de Docker, cuja instalação, configuração e gerenciamento (e, consequentemente, curva de aprendizado) é relativamente mais simples comparando com outras implementações (DOCKER, 2018).