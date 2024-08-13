### Introdução

Existem muitos modelos para gestão de TI, os quais ajudam a melhorar o fluxo das informações e tomadas de decisão (CARVALHO, 1993). O modelo funcional adotado para a gerência do ambiente de redes, está dividido em cinco áreas do conhecimento, conhecidas como gerências, que abordam de forma bem clara as funcionalidades da gerência de cada uma destas áreas.

Estas cinco áreas informa Clemm (2007) são: gerência de falhas, gerência de configuração, gerência de desempenho, gerência de contabilidade e gerência de segurança, por questão de facilidade de aprendizagem essas cinco gerencias formam o mnemônico FCAPS, que são as primeiras letras de cada gerencia no idioma inglês. **FCAPS (**_**faults, configuration, accounting, performance, security**_**).**

A ITU-T introduziu o termo Telecommunications Management Network (TMN), Rede de Gestão de Telecomunicações, para descrever uma rede separada que tem interfaces com a rede de telecomunicações (ou rede de produção). A TMN define pontos de interligação entre as duas redes e especifica as funcionalidades de gestão. A melhor descrição de como operar uma TMN é definida pelas recomendações ITU-T M.3010, M.3400 e X.700.

Esse método de gerência inclui o fornecimento, integração e coordenação de hardware, software e elementos humanos para monitorar, testar, configurar, consultar, analisar, avaliar e controlar a rede e os recursos para atender aos requisitos de desempenho, qualidade de serviço e operação em tempo real dentro de um custo razoável.

“Gerenciamento de Redes inclui o fornecimento, integração e coordenação de hardware, software e elementos humanos para monitorar, testar, configurar, consultar, analisar, avaliar e controlar a rede e recursos para atender os requisitos de desempenho, qualidade de serviço e operação em tempo real dentro de um custo razoável” Kurose (2006).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/4/0/324056/19570.gif)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/4/0/324056/19570.gif)

### Gerência de Falhas.

Para Clemm(2007), define-se gerência de falhas como o processo de localização de problemas, ou falhas, na rede de computadores e correção das mesmas.

Chama-se de falha uma condição anormal apresentada, que requer atenção, e se possível ação gerencial. Chama-se de erro um evento isolado.

Uma falha é geralmente identificada por imperfeições na operação de um sistema, quando o mesmo deixa de operar corretamente ou ainda por erros excessivos, ainda a falha pode ser compreendida como um incidente ou evento que venha acarretar no mau funcionamento do sistema. A identificação e correção de falhas envolve 4 fases:

1. **Detecção** - consiste em determinar a origem da falha.
2. **Determinação** - requer o isolamento da falha do restante da rede, reconfiguração da rede para diminuir o impacto da falha.
3. **Diagnóstico** - envolve análise profunda para um diagnóstico correto, o qual ajude na tomada de decisões as mais assertivas possíveis.
4. **Resolução** - finalmente a ação para reparar ou trocar componentes com falha.

Essas fases têm como objetivo principal detectar e resolver rapidamente situações que degradam o funcionamento da rede, são de suma importância para que uma falha não prejudique o funcionamento de toda a rede, lembrando que a gerência de falhas tem precedência sobre as demais áreas.

Gerência de falhas pode se **reativa** quando reage às falhas na medida em que elas ocorrem, ou **proativa** quando procura-se detectar falhas antes que elas ocorram.

Na fase de **detecção das falhas**, pode-se utilizar agentes instalados nos dispositivos de rede, os quais geram notificações de eventos importantes e polling para informar eventos gerais, essas notificações devem estar armazenadas no sistema de gerenciamento de redes para serem usados como dados históricos, e possíveis correlação de eventos.

Nas fases de **determinação e diagnóstico**, os dados armazenados no sistema de gerenciamento devem ser consultados e devidamente classificadas, comparando o estado atual com os dados histórico, pois nestas fases faz-se necessário verificar se a falha é relevante e procurar a possível causa da falha.

Na fase de **resolução** deve-se aplicar ações de correção da falha e analisar se a falha desapareceu ou não.

Vantagens  de utilizar gerencia de falhas.

- Utilizando corretamente os conceitos de gerência de falhas a confiabilidade da rede aumenta.
- O processo de detecção e recuperação de problemas ocorre mais rapidamente.
- Elimina ou ameniza o comumente chamado "apagar incêndios", pois o conhecimento do comportamento da rede, fica gradativamente mais claro e fácil.

### Classificação das falhas.

É importante saber que as falhas possuem prioridades diferentes, sendo assim, dependendo do impacto da falha sua classificação será diferente.

Exemplo a queda de enlace interno de um switch local e a queda de link da internet da empresa toda, eventos com prioridades diferentes.

Nem todos eventos reportados são ?**falhas?**, sendo necessário a filtragem de eventos.

Pela experiência nas redes mundiais é importante classificar o tamanho da rede pode limitar o número de eventos para análise.

1. **Pequena** - gerência completa de todos os dispositivos.
2. **Média** - gerência apenas dos eventos críticos de cada dispositivo.
3. **Grande** - gerência dos eventos críticos para alguns dispositivos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/2/293270/18300.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/2/293270/18300.png)

Gerência de configuração

### Gerência de configuração.

Gerência de configuração consiste no processo de identificação, localização e configuração dos dispositivos de rede. Para Claise e Wolter (2011) sua função principal é controlar e monitorar as condições do ambiente de rede, através do controle de mudanças que foram efetuadas no estado dos objetos gerenciados, utiliza-se do processo de inventário e back-up das configurações, bem como histórico de mudanças. Alguns itens são de suma importância e devem ser observados:

- Instalação de novos componentes na infraestrutura.
- Alteração de configurações físicas e lógicas da rede.
- Manutenção da lista de equipamentos e softwares instalados.
- Atualização do software de equipamentos.
- Conexões físicas e lógicas entre dispositivos.
- Modo de operação de cada dispositivo.

Gerência de configuração pode ser dividida em três aspectos:

- Com **inventários** que consiste em ter catalogado todos os dispositivos da rede, versões de software e hardware e suas informações estáticas. Exemplo:
    - Inventario de todos os dispositivos - hardware.
    - Inventário de todas as versões de software.
- Com documentação das **configurações**, objetivas e constantemente atualizadas. Exemplo:
    - Back-up de todas configurações atuais e históricas.
    - Leiautes claro e objetivos atualizados das conexões entre os dispositivos.
- Com **provisionamentos**: Parâmetros operacionais modificáveis que especificam o comportamento de cada dispositivo.

### Vantagens de utilizar gerência de configuração.

- Aumenta o controle da configuração dos dispositivos de rede.
- Permite acesso mais rápido e confiável às informações.
- Controle da atualização de configurações de maneira mais eficiente.

### Processos que devem compor um sistema de gerenciamento de configuração.

Existem alguns procedimentos necessários para compor um sistema de gerenciamento de configurações, que são relacionados abaixo.

- Obtenção de informações sobre o ambiente atual da rede.
    - Processo de ?automapping?.
    - Permitir a busca de dispositivos.
- Utilização dos dados para reconfiguração dos dispositivos de rede.
    - Deve permitir a recuperação de configurações anteriores.
    - Gerar advertências para configurações inadequadas.
- Armazenamento dos dados.
    - Arquivos texto, html, ou uma base em sql, Oracle, etc.
- Geração de relatórios gerenciais e técnicos.
    - Configuração completa.
    - Modificações recentes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/7/266766/13821.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/7/266766/13821.jpg)

Gerência de contabilidade

### Gerência de Contabilidade

Gerência de contabilidade tem por função controlar a utilização dos recursos da rede de modo a estabelecer métricas, verificar quotas, determinar custos e taxar os usuários (CARVALHO,1993).

O levantamento do perfil de uso dos recursos permite revelar possíveis abusos de privilégio no uso dos mesmos, auxiliando a melhoria do desempenho e do planejamento de capacidade de utilização da rede.

### Vantagens de utilizar gerência de contabilidade.

Muitas são as vantagens, de se utilizar a gerência de contabilidade, pois a mesma afeta diretamente todas as outras gerencias, por exemplo:

1. No quesito falhas, proporciona filtro de usuários de determinado serviço;
2. No quesito configuração o controle de quem foram os envolvidos em qualquer mudança nos equipamentos;
3. No quesito desempenho limitando acessos indevidos preservando assim recursos que só devem ser acessados por determinados grupos;
4. No quesito segurança mantem os acessos mapeados por conhecer a lista de usuários com dadas permissões.

Bem como foi dito essa gerência é bem utilizada por todas as outras. Na sequência citamos algumas vantagens tangíveis:

- Habilita a medição e documentação de informações de contabilização.
- Permite entender o comportamento de usuários.
- Auxilia na determinação de onde recursos devem ser alocados.
- Ajuda na análise do custo-benefício de novas tecnologias.

### Métodos e boas práticas para a gerência de contabilidade.

- Obter dados de utilização dos recursos da rede, número total de transações realizadas, bytes recebidos/enviados, etc.
- Utilizar métricas para ajudar e definir quotas de uso, podendo se utilizar as seguintes métricas para contabilização: número de transações, número de conexões, número de usuários para dado sistema...
- Repartição justa dos recursos: definição de quotas para usuários ou grupos de usuários, se a quota for excedida pode-se cobrar mais caro pelo uso do recurso.
- Taxar os usuários pelo uso da rede, sendo a taxa mensal fixa. Proporcionar utilização de extratos para cada usuário.
- Utilização de política, para um melhor planejamento, possibilitando:
- Previsões sobre a necessidade de mais recursos
- Previsão sobre utilização de usuário (ou grupo de usuários)
- Dados históricos e tendência corrente de uso.

Uma boa referência de utilização para a gerência de contabilidade é a RFC 1272 - Internet Accounting Background.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296813/19585.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296813/19585.jpg)

Desempenho em redes de computadores

### Gerência de Desempenho

Gerência de desempenho é fundamental para garantir a boa qualidade dos serviços de uma rede de computadores, possui muitos aspectos e trabalha com medição do desempenho de software e hardware da rede, objetivando assegurar que a qualidade da rede. Uma rede com uma boa qualidade permite seus recursos estejam sempre disponíveis e acessíveis  (CLAISE; WOLTER, 2011).

Com a gerência de desempenho pode-se antecipar problemas iminentes, dada uma possível degradação dos indicadores de desempenho. Além disso possibilita-se estabelecer limiares de comportamento permitidos para cada componente, e emitindo notificações para motivar uma ação, quando esses valores forem atingidos.

### Vantagens em utilizar gerência de desempenho.

- Auxilia no oferecimento de um nível de serviço satisfatório aos usuários.
- Monitoração da utilização dos dispositivos de rede e bem como seus recursos como links, linhas, etc.
- Ajuda no planejamento de capacidade da rede.

### Passos necessários para obter uma boa gerencia de desempenho.

- Coleta de dados sobre a utilização dos serviços, dispositivos e links.
- Coleta de dados em tempo real.
- Dispositivos com métricas diferentes.
- Utilização de histórico (logs).
- Análise dos dados relevantes.
- Apresentação dos dados em tempo real.
- Resultado das medidas mostrados em gráficos (histórico).
- Definição de limites de utilização.
- Valor limite (threshold) usado para a geração de eventos (alarmes).
- Simulação da rede.
- Verificar o comportamento da rede em eventuais mudanças.
- Identificação de possíveis melhorias antes de se adquirir novos equipamentos e/ou software.
- Previsão de condições críticas de uso.
- Auxílio em capacity planning – teste de cenários.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/7/8/317859/18070.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/7/8/317859/18070.jpg)

Segurança da informação

### Gerência de segurança.

Num mundo onde informação é a base para o sucesso de todas as empresas e instituições a gerência de segurança é fundamental, essencial e obrigadora.

Gerência de segurança segundo Claise e Wolter (2011) possui muitas atribuições entre elas a de controle de acesso às informações na rede, o que envolve a proteção de dados sensíveis dos dispositivos de rede através do controle de acesso aos pontos onde tais informações se localizam, para que isso seja possível é necessário realizar-se  a identificação dos pontos de acesso e manutenção destes sob constante vigilância, informando inclusive as tentativas de acesso indevido para uma ação preventiva, criando políticas de acesso das informações as quais são sensíveis em relação a necessidade de acesso dos usuários. Na literatura técnica existente uma série de normas que poderão ajudar e devem ser seguidas, abaixo citamos as mais importantes:

- ABNT NBR ISO/IEC 27001:2013 - Sistemas de Gestão de Segurança da Informação (SGSI) – Requisitos;
- ABNT NBR ISO/IEC 27002:2013 - Código de Prática para a Gestão da Segurança da Informação;

### Vantagens em se utilizar a gerência de segurança.

Quando não se tem a gerência de segurança para se manter os dados seguros pensava-se em eliminar o acesso a informações sensíveis através da rede de comunicação de dados. Solução drástica e não prática.

Quando se utiliza a gerência de segurança, pensa-se em várias camadas que vão além da informação em si, mas   por exemplo, em como transferir e armazenar as informações, garantir identificação das pessoas que estão acessando, etc. Camadas como confidencialidade, integridade e disponibilidade.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/1/4/321498/21923.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/1/4/321498/21923.png)

Camadas que envolvem a segurança da informação

### Requisitos necessários para uma boa gerência de segurança.

- Reconhecimento dos pontos cruciais da rede.
    - **Identificação das informações sensíveis.**
        - Definidas pela política da empresa.
        - Identificação das máquinas que guardam tais informações.
    - **Identificação dos pontos de acesso.**
        - Conexão física, login remoto (Telnet), transferência de arquivos (FTP), correio eletrônico (e-mail), execução remota de processos (rsh), servidores de diretórios e arquivos.
        - Qualquer serviço de rede é uma porta de entrada.
    - **Prover segurança para os pontos de acesso.**
        - Pode ser implantada em várias camadas da rede.
- Criptografia, na camada de enlace de dados
    - **Codificação da informação**
    - **Indicada quando o meio é compartilhado**
    - **Algoritmos de chave privada**
        - Mesma chave para codificação e decodificação
        - Chave deve ser trocada periodicamente.
    - **Algoritmos de chave pública**
        - Chaves com duas partes: uma privada e outra pública
        - Codificação feita com chave pública e decodificação com chave privada.
        - DES (Data Encryption Standard)
        - SNMPv2 usa algoritmo de chave pública
- Filtros de pacotes, na camada de rede, para consolidação de informações.
    - **Roteamento de pacotes entre VLANS.**
        - Permitindo seleção de tráfego.
        - Permitindo que determindao tráfego passe ou não pelo Core da rede.
- Autenticação, na camada de aplicação.
    - **Autenticação de Host.**
    - **Autenticação de usuário.**
    - **Autenticação de chave.**
    - **Cofre de senhas.**