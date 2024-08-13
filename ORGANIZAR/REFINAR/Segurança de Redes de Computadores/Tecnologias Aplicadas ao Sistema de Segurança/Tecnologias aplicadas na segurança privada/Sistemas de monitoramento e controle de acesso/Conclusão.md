[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

Com o objetivo de ganhar o contrato da Sider, você deverá apresentar um projeto ao senhor Siderley Chubacy, e nesta primeira fase, o projeto deve se concentrar nas tecnologias de controle de acesso.

Este projeto poderia ser realizado de várias maneiras, com várias proposições diferentes, sendo que se todos os requisitos de segurança são atendidos, o projeto está basicamente correto. Em sua proposição, você deve adicionar uma descrição do ambiente do cliente (no caso, a Sider), de forma a servir de justificativa para os elementos do projeto proposto.

Em que pese haver várias soluções possíveis, uma maneira racional de se propor o projeto é dividi-lo em áreas de atuação, como apresentado a seguir:

**Infraestrutura**

- Rede de comunicação – Por mais que haja soluções de sinalização proprietárias e bastante eficientes, vamos sugerir que a infraestrutura de todas as soluções propostas seja a rede TCP/IP da Sider, de forma que os resultados de coleta de todo o parque de sensoriamento, todas as câmeras, todas as fechaduras eletrônicas, toda a segurança perimetral etc. tenham seus dados concentrados em uma única central de controle, capaz de gerenciar todo o controle de acesso.
    - Os sensores próximos e/ou com acesso ao cabeamento podem ser cabeados para facilitar e baratear o acesso à rede;
    - Os sensores distantes podem ser conectados via Wi-Fi.
- Servidores – Em que pese fazerem parte da mesma infraestrutura de rede TCP/IP, sugere-se que tanto os sensores e equipamentos de controle de acesso e CVTV quanto os servidores (aplicativos, bancos de dados, central de controle) pertençam a uma rede lógica separada, de maneira a não permitir o acesso de terceiros aos dados de segurança e controle de acesso.
- Processo – O pessoal de segurança que opera a Central de Segurança da Sider, bem como o pessoal de campo, deve estar treinado para atuar diante de intercorrências que venham a surgir no ambiente. Os seguranças devem estar treinados para lidar com pessoal sem direito de acesso, tentando entrar no ambiente, pessoal sem direito de acesso identificado fora de sua área de acesso (em violação de direito de acesso), perda e/ou roubo de crachás, preservação de evidências (logs, registros e filmagens).
- Controle de Acesso
    - Crachás Eletrônicos – Crachás de aproximação que identificam o usuário. Esses crachás devem ser pessoais e intransferíveis com uso obrigatório todo o tempo em que o funcionário estiver no ambiente da Sider. São adequados para acesso perimetral, isto é, para locais de uso comum de funcionários da empresa, tais como as portarias de entrada da Sider, os locais de uso comum e de passagem a locais restritos.
    - Leitores Biométricos – Sugerir leitores baseados em digitais para acesso a locais internos sensíveis para o negócio da Sider, tais como laboratórios e salas de trabalho. • Fechaduras Eletrônicas – Para Armários, almoxarifados, salas de suprimentos e mesmo salas de reunião.
    - Portarias Virtuais – Em locais de acesso de pouco trânsito, sem acesso do público, portarias virtuais serão implantadas, conectadas à Central de Controle, com câmeras e leitores faciais permitindo o acesso dos indivíduos autorizados.
    - Sensores de Movimento – Implantados em toda a área interna e externa da Sider, ativos na área interna em locais e horários sem nenhuma circulação, e na área externa 24 h por dia. Conectados e gerando eventos diretamente na Central de Controle.
- Segurança Perimetral
    - Cerca eletrificada com sensores de movimento nos fios externos, identificando tentativas de invasão, e câmeras acopladas a cada 20 metros, com visão de todo o perímetro.

**Circuito Fechado de TV**

- Utilizando câmeras reais em todo o perímetro e em todo o interior da Sider, conectadas à Central de Controle e emitindo suas imagens em tempo real, 2 horas horas por dia, armazenadas em banco de dados e conectadas ao sistema de reconhecimento de face da Sider.

**Central de Controle**

- Console central tipo “telão” com mapa representativo de cada aspecto do local a ser controlado, com eventos em tempo real. A central também deverá ser equipada com mesas com terminais e telefones para os operadores, cuja responsabilidade será análise em tempo real de cada parâmetro em cada ponto de controle.

Desta maneira, tem-se um projeto coerente e coeso de Controle de Acesso para a Sider.