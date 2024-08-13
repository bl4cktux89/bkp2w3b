**Introdução**

Olá, bem-vindos à terceira aula!

Nesta aula vamos ver os modelos de gerência de rede para compreender como uma gerência de redes computacionais é elaborada.

Na aula anterior, falamos sobre o gerente e quais são os seus objetivos. Agora, precisamos estudar alguns modelos para que possamos, no futuro, aplicar as regras, de modo a manter a confiabilidade e a disponibilidade de uma rede.

**Modelo FCAPS**

A partir do desenvolvimento do modelo de referência OSI (ISO), foram definidos conceitos de áreas funcionais, modelos de informação para representar recursos de rede e protocolos para a transferência de informações sobre ela. Do conceito de áreas funcionais criou-se o modelo FCAPS (Fault, Configuration, Accounting, Performance and Security – Falhas, Configuração, Contabilidade, Desempenho e Segurança), que serve de base para todos os demais, pois define as áreas funcionais da gerência de redes:

- **Gerência de Falhas:** responsável pela detecção, isolamento, notificação e correção de falhas na rede.
- **Gerência de Configuração:** responsável pelo registro e manutenção dos parâmetros de configuração dos serviços da rede, tais como informações sobre versões de hardware e de software.
- **Gerência de Contabilidade**: responsável pelo registro do uso da rede, com objetivo de cobrá-lo ou regulamentá-lo.
- **Gerência de Desempenho:** responsável pela medição e disponibilização das informações sobre aspectos do desempenho dos serviços e da própria rede. Esses dados são usados para garantir que a rede opere em conformidade com a qualidade de serviço acordados com seus usuários, como também para análise de tendências.
- **Gerência de Segurança:** responsável por restringir o acesso à rede e impedir seu uso incorreto, de forma intencional ou não.

**Modelo TMN**

É um modelo de gerenciamento de redes de telecomunicações, padronizado pela ITU-T, com a finalidade de fornecer um conjunto de funções que permitem realizar a gerência e a administração de uma rede de telecomunicações, a qual compreende planejamento, provisionamento, instalação, manutenção, operação e administração.

O objetivo do modelo Telecommunication Network Management (TMN) é fornecer uma arquitetura organizada, que permita interligar diversos tipos de sistema de operação de gerência de equipamentos e telecomunicação pelo uso de interfaces, protocolos e mensagens padronizadas. Com isso, é possível interligar elementos e sistemas heterogêneos de diversos fabricantes, fazendo com que todos os componentes, tais como redes locais, de longa distância, metropolitanas, PABX e dispositivos de telefonia móvel possam ser gerenciados de forma integrada.

O modelo TMN é empregado principalmente por operadores de serviços de telecomunicações.

**Modelo TOM**

É um modelo de gerência de redes criado pelo Telemanagement Fórum para substituir o modelo TMN. O Telecom Operation Map (TOM) define modelos de processos para criação de novos sistemas e softwares, integrando padrões comerciais para criação de serviços. Sua estrutura é dividida em processos operacionais, estratégicos, infraestrutura, produto e gestão empresarial.

**Modelo OAM&P**

Operation, Administration, Maintenance and Provisioning é um modelo de gerência para operações de rotina, em um ambiente de rede que detecta, diagnostica e corrige falhas, mantendo o funcionamento do sistema. A administração envolve o planejamento da rede em longo prazo, dados estatísticos, estratégia e tendências. A manutenção envolve atualizações, correções, backup, equipamentos, tarefas que provocam a paralisação da rede por certo período, necessitando de um planejamento para não gerar um impacto maior. O provisionamento refere-se à remoção ou criação de estabelecimento de serviços e abrange instalações de equipamentos.

**Modelo CMIP/CMIS**

Common Management Information Protocol/Common Management Information Service é um modelo usado pelos principais operadores de telecomunicação, criando um mapa de projeto do sistema de gerência da rede. O CMIP/CMIS é originário da arquitetura OSI. O CMIS define o gerenciamento dos serviços e o CMIP define a forma de transmissão e a sintaxe desse gerenciamento.

**Modelo SNMP**

Simple Network Management Protocol é o modelo de gerência mais usado no mundo. Apesar de seu nome sugerir simplicidade, o gerenciamento de redes, especialmente na Internet, é muito mais do que apenas um protocolo para transportar dados de gerenciamento entre uma entidade gerenciadora e seus agentes, e o SNMP passou a ser muito mais complexo do que a palavra "Simples" de seu nome.

O SNMP é composto por quatro componentes: nós gerenciados, estações e informações de gerenciamento e um protocolo. Apesar da evolução e da complexidade das redes atuais, esses componentes são a base desse modelo.

Na próxima aula falaremos mais sobre o FCAPS e a partir dele trabalharemos o SNMP, sua arquitetura, protocolo e versões, por se tratar da estrutura mais difundida e comumente usada nos ambientes de rede, já que a grande maioria trabalha com a arquitetura TCP/IP ou é compatível com ela.

Caso fique alguma dúvida, leve a questão ao Fórum e divida-a com seus colegas e professor.