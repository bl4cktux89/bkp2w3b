### **Introdução**

Um incidente relacionado a segurança computacional e a redes de computadores é um evento que testa a segurança de soluções computacionais que operam em uma rede. Os resultados decorrentes de um incidente de segurança podem ter diferentes resultados, que vão de fraude, vazamento de informações ou até mesmo a destruição dos recursos da rede.

O gerenciamento de incidentes passa pela análise dos sistemas de detecção de intrusão (IDSs) e diferentes tecnologias de firewall. A resposta a esses incidentes passa por diferentes fases e requer um planejamento das organizações com base em políticas formais de tratamento de incidentes.

A gestão de risco permite as organizações preverem a extensão dos danos ocasionados pelo incidente, tendo em vista que uma ameaça pode ter alcances diferentes para cada organização. Esses danos podem levar a oscilação e inoperância temporária do funcionamento de uma rede.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/5/1/5/8/1515883/37194.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/5/1/5/8/1515883/37194.jpg)

Gerenciamento de incidentes

### Tipos de Incidentes

Cada organização deve ter o conhecimento do conjunto de seus recursos e suas respectivas vulnerabilidades associadas, de forma a ter classificado o nível de esforço necessário para se recuperar de um incidente danoso. A avaliação de risco reflete o grau de impacto e a probabilidade de ocorrência de dano resultante de cada vulnerabilidade. É listado abaixo alguns incidentes que podem indicar a ocorrer às redes de computadores (McNab, Chris, 2017).

- **Erros e omissões**: Os erros e omissões refere-se, por exemplo, a instalação e configuração incorreta de ferramentas que deixam brechas de segurança.
- **Fraude e roubo**: Podem ser executados por meio de ferramentas e funcionários descontes que possuem um bom conhecimento sobre a hierarquia funcional e operacional.
- **Intrusão silenciosa**: ocorrem quando um agente malicioso invade a rede de forma a não ser detectável com o objetivo de coletar informações, de corromper dados e de identificar e criar portas de entrada.
- **Ataques DoS**: Ataques que exploram as vulnerabilidades do TCP/IP e falhas no projeto de aplicações, gerando pacotes malformados que podem ocasionar estouro de buffer, inundação na rede e erros de pilha.
- **Páginas modificadas**: o invasor raqueia um servidor web com o objetivo de alterar de forma discreta ou não a páginas de organizações, provocando perdas de receitas, de reputação e moral.
- **Código malicioso**: por meio de cavalos de troia, vermes e vírus, um agente mal intencionado podem coletar informações do sistema, provocar inoperância na rede ou criar portas de entrada.

Alguns eventos podem indicar que um ataque está em curso na rede:

- Redução na velocidade da rede pode ser indício de um ataque de DoS
- Ataques de negação de serviço (DoS) levam a execução de processos incomuns que utilizam recursos da rede.
- Ataques que fazem uso de vírus e vermes podem levar a mau funcionamento dos computadores, levando a padrões de reclamações por parte dos funcionários.
- Solicitações de autenticação de endereços IPs que não fazem parte dos endereços IPs permitidos.

### Detecção de Incidentes

O monitoramento constitui de elemento fundamental para a detecção de incidentes. É extremamente importante que a rede seja monitorada constantemente, seja através de uma abordagem reativa que surge a partir da detecção de mau funcionamento da rede ou de reclamações de funcionários; ou através de uma abordagem ativa utilizando de ferramentas que estão constantemente monitorando como os IDS.

Na sequência, o incidente deve ser analisado em seus detalhes a fim de verificar se a um incidente pode ser benigno ou necessita da equipe de resposta a incidentes.

Além desses passos, é importante mencionar alguns procedimentos específicos a ser incorporados a fim de garantir que os incidentes sejam detectados antes que ocasione danos a redes (Basta, A; Basta, N. Brown, M. 2015):

- Proporcionar segurança em camadas por meio de diversos controles preventivos.
- Implementar de ferramentas de monitoramento de acordo com as características da rede, estando elas sempre atualizadas e com os patchs de segurança instalados.
- Armazenar arquivos confidenciais em locais seguros e monitorando esse local de forma constante.
- Manter uma base de dados de informações de registro de sistemas de todos os recursos da rede, e comparando-as em busca de possíveis ataques.

### Fases do tratamento de incidentes

As fases para o tratamento de incidentes são descritas abaixo com base no fluxograma que segue (Basta, A; Basta, N. Brown, M. 2015):

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/0/6/9/0/8069025/59295.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/8/0/6/9/0/8069025/59295.jpg)

Fluxograma das fases para o tratamento de incidente

Fonte: Basta, A; Basta, N. Brown, M. 2015. Segurança de Computadores e teste de invasão. São Paulo: Cengage Learning, 2015)

1. **Preparação:** Consiste em desenvolver um inventário de recursos, classificando-os de acordo com seu valor para a organização, levando em consideração o valor do ativo e custo para protegê-lo. Além disso é necessário que a organização tenha uma política de tratamento de incidentes e uma equipe de tratamento de incidentes.  
2.  
**Classificação de incidentes:** tem por finalidade identificar se realmente existe a ocorrência de um incidente. Em caso positivo, como se classifica em termos de importância e consequentemente determinar quais recursos deverão ser empregados para solucioná-lo  
3.  
**Determinação do impacto**: identificar a partir do inventário quais ativos são fundamentais para continuidade do processo de negócio da organização. Este item pode ser avaliado pelo número de recursos (por exemplo computadores) envolvidos no incidente.  
4.  
**Definição da probabilidade**: deve-se relacionar a determinação do impacto, determinado anteriormente, com a probabilidade desse incidente ocorrer. Isso pode ser gerenciado por uma matriz de avaliação de risco, conforme tabela que segue.

![[Untitled 97.png|Untitled 97.png]]

1. **Erradicação:** uma das primeiras etapas para erradicar consiste no arquivamento do estado atual da máquina afetada e de seus arquivos. Essa ação tem finalidade determinar a possível rastreabilidade do agente causador e de portas abertas. Na sequência corrige-se o problema, levando sempre em consideração a análise de incidentes anteriores.  
2.  
**Recuperação:** consiste em recuperar do incidente sem danos permanentes, tendo ainda as seguintes etapas: reinstalação, reautenticação, escaneamento para verificar a erradicação do problema e a reativação do sistema.  
3.  
**Pós-morte:** é importante aprender com os erros e acertos. As etapas para concretizar esse aprendizado consiste de: identificar a raiz do problema, incorporar alterações em curto e longo prazo, incorporar ações para incidentes imprevisíveis e aprender com o problema.

**SAIBA MAIS...**

O Centro de Estudos, Resposta e Tratamento de Incidentes de Segurança no Brasil é mantido pelo [**NIC.br**](http://www.nic.br/), do [**Comitê Gestor da Internet no Brasil**](http://www.cgi.br/), e atende a qualquer rede brasileira conectada à Internet. Acesse: [**https://www.cert.br/**](https://www.cert.br/)