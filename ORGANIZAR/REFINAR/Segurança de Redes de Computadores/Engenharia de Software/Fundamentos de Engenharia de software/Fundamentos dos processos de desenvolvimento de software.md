# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/14189f36-31f4-4be2-a19f-fd47689db714/original)](https://ampli-images.s3.amazonaws.com/production/14189f36-31f4-4be2-a19f-fd47689db714/original)

### **Qual é o foco da aula?**

Nesta aula, você deverá dominar os conceitos de processo de desenvolvimento de _software_ e conhecer seu ciclo de vida tradicional.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- explicar os processos de desenvolvimento de _software_;
- examinar os requisitos para o desenvolvimento;
- Analisar como ocorrem os processos, desde o planejamento até a manutenção.

**Situação-problema**

Nesta segunda aula, retomaremos a situação abordada na aula anterior. Com o crescimento da _XAX-Sooft_, a condução sistemática e correta de um processo de desenvolvimento deverá ganhar importância destacada na empresa. No cenário atual, há risco de perda de controle dos projetos por conta da desorganização na aplicação dos procedimentos vigentes. Nós sabemos que esses procedimentos eram minimamente adequados para a realidade da empresa no início das suas atividades, quando os projetos eram simples e demandavam pouco esforço da equipe.

Uma metodologia formal de desenvolvimento deverá ser escolhida para fins de sistematização dos procedimentos de desenvolvimento de _software_. Será nossa missão dar bons motivos para que os envolvidos nos projetos a adotem e os dirigentes a comuniquem aos colaboradores.

Feito o levantamento dos procedimentos adotados atualmente na _XAX-Sooft_, é hora de você propor soluções para melhoria do processo de desenvolvimento praticado na empresa, utilizando os conhecimentos adquiridos nesta aula.

Esta nova parte do nosso material pretende oferecer soluções viáveis para situações em que o desenvolvimento do sistema passa por dificuldades e incertezas, bem destacadas em nosso estudo sobre a crise do _software_. Sem procedimentos formais, alguns erros comuns poderão ser cometidos mais do que uma vez durante o desenvolvimento, a necessidade de retrabalho estará sempre presente, as ações de prevenção de erros dificilmente serão implantadas e, mais importante, o cliente não estará satisfeito com o produto entregue.

Nosso desafio agora é estruturar as novas práticas, cuidando para que a equipe toda se sinta motivada a adotá-las e a cuidar da sua manutenção e evolução. Os desenvolvedores já se acostumaram à não formalidade dos seus meios e neles confiam, já que, bem ou mal, têm funcionado até o momento. Esse cenário impõe necessidade de planejamento, método e comunicação eficiente sobre a nova metodologia. O estudo do ciclo de vida de um _software_ e de seu processo de desenvolvimento é ponto de partida para a inflexão que a empresa precisa. O que é um processo de _software_? Como implantá-lo de forma eficiente? Vamos adiante!

# **O processo de desenvolvimento de um software**

[![](https://ampli-images.s3.amazonaws.com/production/caa8bb18-3896-4077-88a3-f92a6267f5b6/original)](https://ampli-images.s3.amazonaws.com/production/caa8bb18-3896-4077-88a3-f92a6267f5b6/original)

Conforme já mencionamos, o desenvolvimento de um _software_ pode ser considerado como um processo e não um conjunto de ações isoladas. A previsibilidade e a economia de recursos propiciada por um processo bem estruturado conferem segurança ao desenvolvimento. Ao resumirmos e agruparmos os muitos conceitos que a literatura disponibiliza, teremos que, no âmbito da Engenharia de _Software_, processo é a sequência de passos que visam a produção e manutenção de um _software_ e que se inter-relacionam com recursos (humanos e materiais), com padrões, com entradas e saídas e com a própria estrutura da organização.

Esse conceito pode ser estendido a outros ramos da atividade humana, como a fabricação de um bem de consumo. A figura abaixo mostra o processo de montagem de um automóvel.

[![](https://ampli-images.s3.amazonaws.com/production/26fb758d-b81f-43b8-b54c-616347dfc99e/original)](https://ampli-images.s3.amazonaws.com/production/26fb758d-b81f-43b8-b54c-616347dfc99e/original)

Processo de montagem de um automóvel. Fonte: Pixabay.

O termo “projeto”, comumente utilizado neste âmbito, precisa ser diferenciado de “processo”. De acordo com o Guia do Conhecimento em Gerenciamento de Projetos (PMBOK, 2013, n. p.), projeto:

> "é um conjunto de atividades temporárias, realizadas em grupo, destinadas a produzir um produto, serviço ou resultado únicos".

Ensina Wazlawick (2013), que processo é o conjunto de regras que definem como um projeto deve ser executado. Um processo é adotado pela organização para que seja praticado e aperfeiçoado pelos seus colaboradores durante o desenvolvimento de um projeto.

Ainda de acordo com Wazlawick (2013), há vantagens em se definir o desenvolvimento de _software_ como um processo. O autor apresenta três delas:

**a**) redução no tempo de treinamento, já que funções e procedimentos bem definidos e documentados facilitam a inclusão de novo membro na equipe de trabalho;

**b**) produção de artefatos mais uniformizados, já que a previsibilidade do processo ajuda a equipe a trabalhar de forma mais padronizada;

**c**) transformação de experiências em valor, já que a sistemática utilização do procedimento poderá aperfeiçoá-lo com o tempo.

# **Divisões de estrutura**

[![](https://ampli-images.s3.amazonaws.com/production/6b0e3ad5-8991-4409-91cd-9bbd6107e78f/original)](https://ampli-images.s3.amazonaws.com/production/6b0e3ad5-8991-4409-91cd-9bbd6107e78f/original)

Os processos podem conter divisões em sua estrutura. Para iniciarmos efetivamente o estudo do processo de _software_, convém analisarmos algumas delas.

- **Fases**: um conjunto de atividades afins e com objetivos bem definidos são realizados em uma fase do processo. O modelo cascata de desenvolvimento, por exemplo, apresenta fases bem definidas, quais sejam a fase dos requisitos, a fase do projeto, da programação e assim por diante (WAZLAWICK, 2013).
- **Atividades ou tarefas**: comumente descritas com conceitos semelhantes, uma atividade ou uma tarefa constitui um projeto em pequena escala. Ela visa promover modificações nos artefatos do processo, que podem ser descritos como diagramas, documentos, programas e tudo o que puder ser desenvolvido no processo. As atividades devem possuir entradas, saídas, responsáveis, participantes e recursos bem definidos (WAZLAWICK, 2013).

Em suas regras processuais, a organização pode determinar que seja adotado um documento que descreva a atividade. Por meio dele, a equipe tomará conhecimento da tarefa, seus responsáveis, objetivos, recursos a serem utilizados e tudo o que a caracteriza por completo.

Sabemos até o momento que um processo é um conjunto disciplinado e articulado de tarefas, que serve para sistematizar o desenvolvimento de _software_. Esse tipo de processo é genérico, sendo definido e aplicado pela organização, o que o torna, de certo modo, sua filosofia de trabalho.

Há, no entanto, certos modelos de processos ditos prescritivos, que contêm descrições de como as atividades são realizadas. O modelo Cascata, também conhecido como modelo tradicional, é o mais conhecido e ainda bastante utilizado para desenvolvimento de produtos de _software_. Ele descreve, por meio de etapas bem definidas, o ciclo que o _software_ cumprirá durante o período compreendido entre sua concepção e sua descontinuidade.

O ciclo de vida natural de um _software_, de acordo com Rezende (2005), abrange as seguintes fases: concepção, construção, implantação, implementações, maturidade, declínio, manutenção e descontinuidade. Estas fases são mais comumente descritas como fase de requisitos, projeto, implementação, teste e manutenção. A figura abaixo mostra esquema geral das fases do modelo Cascata.

[![](https://ampli-images.s3.amazonaws.com/production/96d0fd7f-33f5-43e4-a837-7a6e0ea98d32/original)](https://ampli-images.s3.amazonaws.com/production/96d0fd7f-33f5-43e4-a837-7a6e0ea98d32/original)

Representação das fases do modelo Cascata. Fonte: elaborada pelo autor.

Note que uma fase do processo depende do resultado ou do produto gerado pela fase anterior. As setas de retroalimentação, dispostas no sentido contrário à cascata, indicam a possibilidade de retornos às fases anteriores, considerando nelas a ocorrência de falhas. Em outras palavras, o retrocesso a uma fase anterior serve, em tese, para sanar problemas que, se levados adiante, acarretariam mais prejuízo ao desenvolvimento.

______

**🔁 Assimile**

Um ciclo de desenvolvimento de sistemas mais detalhado é apresentado por Rezende (2005), como segue:

Estudo de viabilidade, análise de sistemas, projeto, implementação, geração de teste de aceite, garantia de qualidade, descrição de procedimentos, conversão de bases de dados e instalação.

______

Para que a proposta de ensino desta aula seja contemplada, descreveremos sinteticamente cada uma das fases que, nas aulas seguintes, serão mais bem detalhadas.

# **Requisitos**

[![](https://ampli-images.s3.amazonaws.com/production/b801f8a2-8b02-450e-929d-c898d4527873/original)](https://ampli-images.s3.amazonaws.com/production/b801f8a2-8b02-450e-929d-c898d4527873/original)

A fase de requisitos de _software_ preocupa-se com a descoberta, análise, especificação e validação das propriedades que devem ser apresentadas para resolver tarefas relacionadas ao _software_ que será desenvolvido.

Requisitos são as condições necessárias para que um determinado evento aconteça. Tome como exemplo uma aula presencial de Engenharia de _Software_. Para que ela aconteça, é necessário professor, estudantes, lousa, giz, carteiras. Todos esses itens formam o conjunto de requisitos da aula. No desenvolvimento de _software_ acontece o mesmo. Fazem parte dos requisitos de um _software_ suas funções, suas características, restrições e todas as demais condições para que ele exista e cumpra seu objetivo.

O projeto de um _software_ fica vulnerável quando o levantamento dos requisitos é executado de forma não apropriada. Os requisitos expressam as necessidades e restrições colocadas num produto de _software_ que contribuem para a solução de algum problema do mundo real.

_____

**💭 Reflita**

Caso uma falha seja cometida na fase de levantamento dos requisitos do produto, ela deverá se propagar nas fases seguintes de projeto e implementação. Assim, quanto antes a falha for corrigida, menos dispendioso seu reparo será. Schach (2008) assinala que 60% a 70% de todas as falhas detectadas em grandes projetos acontecem nas fases de levantamentos de requisitos, análise ou de projeto.

Durante 203 inspeções do _software_ da Jet Propulsion Laboratory para o programa interplanetário não tripulado da NASA, em média foram detectadas cerca de 1,9 falhas por página de um documento de especificações, 0,9 falha por página de um projeto, mas apenas 0,3 falha por página de código.

_____

Na definição dos requisitos, o profissional envolvido (chamado de especialista em requisitos, engenheiro de _software_ ou analista de requisitos) tem a oportunidade de aprimorar a alocação das funções do _software_, além de supri-lo com a especificação de requisitos, documento fundamental no relacionamento cliente/desenvolvedor.

_____

**📝 Exemplificando**

Um bom exemplo de como ações simples podem evitar grandes transtornos durante e depois do desenvolvimento de um _software_ pode ser resumido como segue. Logo após concluir o levantamento dos requisitos junto ao cliente e sua posterior análise e especificação, uma certa empresa de desenvolvimento iniciava imediatamente a fase de projeto.

A certeza de que tudo que haviam conversado com o cliente havia sido corretamente compreendido os autorizava a investir pouco tempo no projeto e, sem demora, começar a fase de programação. Ocorre que, com a sucessão de retrabalhos em seus projetos, decidiram rever o processo desde o início.

O que poderia estar errado? Conforme será abordado em detalhes na próxima aula, o processo de requisitos inclui também a validação do que foi definido como funcionalidade do sistema, antes que a elaboração do projeto seja iniciada. Antes de qualquer nova ação, há que se validar os requisitos, o que significa conferi-los em reuniões com as equipes e, principalmente com o cliente.

A partir do momento que a empresa passou a incluir a conferência dos requisitos antes de dar o próximo passo no projeto, a quantidade de retrabalho diminuiu, na mesma proporção em que a comunicação com o cliente melhorou.

# **Projeto, implementação, testes e manutenção**

[![](https://ampli-images.s3.amazonaws.com/production/d7fcf2f4-e0b8-45f7-a540-5133084ac479/original)](https://ampli-images.s3.amazonaws.com/production/d7fcf2f4-e0b8-45f7-a540-5133084ac479/original)

Uma vez levantados, analisados, especificados e validados os requisitos, o processo deverá nos levar ao desenho do produto. Se os requisitos nos mostram “o que” o sistema deverá fazer, **o projeto** deverá refletir “como” ele o fará. Por meio do projeto, os requisitos são refinados de modo a se tornarem aptos a serem transformados em programa.

O trabalho principal de um projetista é o de decompor o produto em módulos, que podem ser conceituados como blocos de código que se comunicam com outros blocos por meio de interfaces.

Na fase de **implementação**, o projeto é transformado em linguagem de programação para que, de fato, o produto passe a ser executável. Para que se possa avaliar se os requisitos foram corretamente traduzidos, a equipe pode optar por construir protótipo do sistema, ou seja, uma versão com funcionalidades apenas de tela para proporcionar entendimento e validação das entradas e saídas do _software_.

Como estratégia de implementação, a equipe poderá dividir o trabalho de forma que cada programador (ou um pequeno grupo deles) fique responsável por um módulo do sistema. Idealmente, a documentação gerada pela fase de projeto deve servir como principal embasamento para a codificação, o que não afasta a necessidade de novas consultas ao cliente e à equipe de projetistas.

**Testar** significa executar um programa com o objetivo de revelar a presença de defeitos. Caso esse objetivo não possa ser cumprido, considera-se o aumento da confiança sobre o programa. O processo de teste deve incluir seu planejamento, projeto de casos de teste, execução do programa com os casos de teste e análise de resultados.

As técnicas Funcional e Estrutural são duas das mais utilizadas técnicas de se testar um _software_. A primeira baseia-se na especificação do _software_ para derivar os requisitos de teste e a segunda baseia-se no conhecimento da estrutura interna (implementação) do programa.

Os esforços de desenvolvimento de um _software_ resultam na entrega de um produto que satisfaça os requisitos do usuário. Espera-se, contudo, que o _software_ sofra alterações e evolua. Uma vez em operação, defeitos são descobertos, ambientes operacionais mudam, e novos requisitos dos usuários vêm à tona. **A manutenção** é parte integrante do ciclo de vida do _software_ e deve receber o mesmo grau de atenção que outras fases.

A manutenção de _software_ é definida como modificações em um produto de _software_ após a entrega ao cliente a fim de corrigir falhas, melhorar o desempenho ou adaptar o produto a um ambiente diferente daquele em que o sistema foi construído.

_____

**💪 Faça você mesmo**

Na primeira aula da unidade anterior foi solicitado que você descrevesse seu primeiro passo caso recebesse a missão de construir o sistema acadêmico da faculdade de seu amigo. No contexto em que se apresentava o exercício, você tinha pouco conhecimento de processo de _software_ e do ciclo de vida de um produto

O desafio agora é que você refaça aquele exercício, colocando em prática o que você já conhece da teoria necessária para iniciar o desenvolvimento de um sistema. Mãos à obra!

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/68113b61-e3c2-407d-afcd-97e007f0e88a/original)](https://ampli-images.s3.amazonaws.com/production/68113b61-e3c2-407d-afcd-97e007f0e88a/original)

Com o levantamento da atual situação em mãos, a _XAX-Sooft_ precisa agora definir procedimento padronizado e universal para construção de seus produtos. A fase do desenvolvimento artesanal e baseado apenas na experiência acumulada de sua equipe deve ficar para trás. Os gestores definiram que qualquer novo procedimento deve ser implantado gradualmente e a necessidade de evolução do processo deve ser considerada, a fim de terem, depois de um ano, um processo sedimentado, amplamente praticado e em constante evolução.

Como podemos, então, iniciar a implantação de um procedimento uniforme?

A primeira providência é definir que as novas práticas devem ser agrupadas e registradas em documento próprio. Este documento conterá as seguintes grandes seções:

1. **Introdução e objetivo:** aqui será descrito o objetivo do documento, que é justamente a definição do procedimento padrão da empresa. Deverá ficar evidente que o processo prescritivo a ser adotado é o modelo tradicional de desenvolvimento.
2. **Definição dos papéis**: nesta seção cada função da equipe será descrita. As características pessoais de cada membro da equipe devem ser levadas em conta no momento de definir áreas de atuação. Quem já tinha facilidade em se relacionar com o cliente deverá ser destacado para a fase de requisitos; o programador experiente deverá continuar a ser líder na fase de implementação e assim por diante. Serão considerados como funções da equipe: engenheiro de requisitos, projetista e desenvolvedor. Este último deverá também ser destacado nas atividades de teste e manutenção.
3. **Definição detalhada do processo de desenvolvimento**: por fim, nesta seção serão definidos os caminhos para a produção de _software_ de qualidade. O processo deverá prever que:

**3.1**. Definida a viabilidade de se assumir o trabalho, a criação do produto deverá ser iniciada pela fase de levantamento e tratamento dos requisitos. Um profissional previamente destacado deverá visitar o cliente e, por meio de reuniões presenciais, coletar todas as suas necessidades em relação ao programa. Os requisitos então serão consolidados em documento e revisados pela equipe.

**3.2**. Levantados os requisitos, um projeto modular do sistema deverá ser criado. Os grandes módulos e suas interfaces deverão ser definidas e um desenho do produto deverá ser gerado.

**3.3**. Dependendo da complexidade e da extensão do produto, os módulos definidos na fase de projeto são distribuídos para um ou mais desenvolvedores para tradução em linguagem de programação.

**3.4**. Terminada a implementação do módulo, os desenvolvedores envolvidos deverão delegar aos colegas a tarefa de testar suas funções, com base nos requisitos revisados. Terminados esses testes, o sistema é integrado e o teste geral é aplicado. Havendo necessidade, os desenvolvedores darão suporte à manutenção ao sistema.

Em todas as fases do processo, prazo e recursos necessários deverão ser explicitados.

_____

**⚠️ Atenção**

Sintetizar o novo processo de desenvolvimento em documento é a melhor providência a se tomar. Ele servirá, inclusive, de referência para novos colaboradores e como fonte de consulta em caso de dúvida sobre os procedimentos.

_____

A especificação dos requisitos se dá pela criação de documento que os contém e define. Um exemplo de documento de especificação de requisitos pode ser encontrado [clicando aqui](https://www.cin.ufpe.br/~rpgl/smartclinic/documentoRequisitos.doc).