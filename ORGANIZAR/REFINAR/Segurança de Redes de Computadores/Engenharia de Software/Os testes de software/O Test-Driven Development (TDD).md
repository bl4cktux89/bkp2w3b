# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/819996c0-8b9e-4d82-8e84-5ca5cefe04a7/original)](https://ampli-images.s3.amazonaws.com/production/819996c0-8b9e-4d82-8e84-5ca5cefe04a7/original)

### **Qual é o foco da aula?**

Nesta aula, tratará do caminho que um erro percorre após sua identificação e os responsáveis por cada ação empreendida para corrigi-lo.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- examinar como funciona a engenharia de testes;
- explicar o ciclo de vida de um erro;
- analisar os modelos de cascata e TDD.

**Situação-problema**

Além de introduzir conceitos fundamentais de teste, nossa última aula serviu para desconstruir a impressão de que verificação em um programa pode ser feita apenas ao se vasculhar o código ou executar o programa algumas vezes, sem critério ou formalidade. Duas das formas mais comuns de executar verificações num _software_ – o teste funcional e o teste estrutural – foram introduzidas e a importância da correta escolha de casos de teste foi destacada.

Pois bem, a percepção geral na _XAX-Sooft_ é que a introdução de procedimento formal de teste começará em breve a produzir bons resultados. A fase inicial do novo procedimento incluiu a seleção de casos de teste e aquele desafio tornou você e a equipe de desenvolvimento aptos para dar continuidade ao processo de teste. O desafio que se coloca nesta aula é a efetiva aplicação do teste funcional em um dos produtos da _XAX-Sooft_, incluindo o relato das atividades desempenhadas e as ações empreendidas pelos envolvidos no procedimento.

Além de fornecer nova abordagem do _Test-Driven Development (TDD)_ e apresentar esta técnica como própria do modelo ágil de desenvolvimento, é também objetivo desta aula apresentar o tratamento que um erro encontrado por um testador recebe após sua descoberta. Esse tratamento desenhará o que chamaremos de ciclo de vida de um erro e você, na condição de participante ativo do processo de teste, será convidado a sugerir aprimoramentos no desenho desse ciclo, que nasce na descoberta do erro e termina em sua completa correção.

Com esse conteúdo, você seguirá aprimorando sua competência para conhecer e conduzir processos de testes de _software_, sempre mirando a excelência nos procedimentos e na qualidade dos produtos da _XAX-Sooft_.

Adiante e bom trabalho!

# **Engenharia de Testes**

[![](https://ampli-images.s3.amazonaws.com/production/33d2c4d4-ae67-44f6-bf82-8429f5a86a73/original)](https://ampli-images.s3.amazonaws.com/production/33d2c4d4-ae67-44f6-bf82-8429f5a86a73/original)

Em nossa última aula, quando tratamos de temas iniciais de teste de _software_, foi dada ênfase às definições de defeito, erro e falha. Entre um exemplo e outro, o texto procurou deixar clara a sutileza entre os conceitos, sem que as diferenças entre os três se perdessem. No entanto, fora dos limites da esfera acadêmica, qualquer problema que se manifeste no código tende a ser chamado simplesmente de bug, ou como referenciaremos aqui, de erro.

A intenção do que chamamos de Engenharia de Testes é simples: oferecer entendimento do que é um erro e oferecer formas de encontrá-lo.

Em aulas anteriores, foi discutida a impossibilidade de assegurar a completa e irrestrita ausência de erros em um programa, justamente pela condição falível dos programadores. Mas será que apenas os programadores falham?

Um erro ocorre quando uma ou mais das opções a seguir for verdadeira (PINHEIRO, 2015):

- o _software_ não faz algo que a especificação estabelece que ele deveria fazer;
- o _software_ faz algo que a especificação estabelece que ele não deveria fazer;
- o _software_ faz algo que a especificação não menciona;
- o _software_ não faz algo que a especificação não menciona, mas deveria mencionar;
- o _software_ é difícil de usar, entender ou, na visão do testador, pode ser visto pelo usuário final como não estando correto.

Fica claro que a especificação incorreta é uma das grandes causas de erros em programas. Mas não só ela. Em sistemas pequenos, erros na codificação respondem por aproximadamente 75% das ocorrências. A tendência é simples de ser entendida: quanto maior o projeto, menor a quantidade de erros na codificação e maior na especificação.

Pelo seu alto potencial em causar problema para equipe e clientes, muito se investe na busca por um perfil ou um padrão na ocorrência de erros. Sabe-se que 85% dos erros podem ser corrigidos em uma hora. É sabido que 80% do esforço é concentrado em apenas 20% do código, o que nos leva ao raciocínio de que os erros estão concentrados em partes específicas do código (PINHEIRO, 2015).

# **O ciclo de vida de um erro**

[![](https://ampli-images.s3.amazonaws.com/production/bf342294-a238-454b-8c2e-f66c15058942/original)](https://ampli-images.s3.amazonaws.com/production/bf342294-a238-454b-8c2e-f66c15058942/original)

Compreende o período entre a identificação do erro e sua efetiva correção, sempre durante o processo de testes.

Em cada fase de seu ciclo, o erro recebe uma denominação diferente, providência importante para que os envolvidos identifiquem seu estado com rapidez e correção. O ciclo inclui os seguintes estados, descritos no quadro abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/d2b51e72-3033-495f-886d-fd09f25076e8/original)](https://ampli-images.s3.amazonaws.com/production/d2b51e72-3033-495f-886d-fd09f25076e8/original)

Estados assumidos por um erro em seu ciclo de vida. Fonte: Learn data modeling.

_____

**📝 Exemplificando**

Vamos ao exemplo de como o erro percorre seu caminho da descoberta até sua correção. Imagine um aplicativo de envio de e-mail sendo testado. Assim que o programa é terminado, o responsável confere a página de login e descobre que o campo de nome de usuário permite nomes duplicados.

A partir da constatação, o responsável registra o erro e o reporta ao líder do teste. O líder então verifica o erro e, caso o valide, este receberá o status de “novo” e será passado à equipe de desenvolvimento. O líder da equipe de desenvolvimento faz nova verificação e, se for constatado que se trata de fato de um erro no programa, o erro é atribuído a um desenvolvedor – no caso um especialista em banco de dados – para correção. O desenvolvedor cria uma chave primária na tabela, altera o status do erro para “corrigido” e reporta a ação para o líder do teste que, por sua vez, muda o status para “novo teste” e atribui a tarefa de revisão a um testador. Se, depois disso, o erro tiver sido sanado, seu status passará para “fechado”.

_____

Como o caminho entre a descoberta do erro e sua efetiva correção percorre um caminho definido, podemos representá-lo conforme ilustrado na figura abaixo. Observe o fluxo:

[![](https://ampli-images.s3.amazonaws.com/production/ce94d20c-bbf1-42bc-9cd1-477fcc58066f/original)](https://ampli-images.s3.amazonaws.com/production/ce94d20c-bbf1-42bc-9cd1-477fcc58066f/original)

Fluxograma de ações para tratamento de um erro. Fonte: Learn data modeling.

Pois bem, esse é um meio possível de se tratar um erro. Sejam quais forem as ações escolhidas, elas devem ser registradas, estruturadas e, naturalmente, desempenhadas por todos os envolvidos no processo de teste.

Há, no entanto, algumas outras situações que podem ocorrer durante o tratamento de um erro. Vejamos:

- o testador reporta um erro ao líder do teste, que não interpreta a situação como erro e o rejeita;
- o líder do teste valida o erro encontrado pelo testador e o reporta ao líder do desenvolvimento, que o rejeita;
- tanto o líder do teste quanto o líder do desenvolvimento validam o erro. O desenvolvedor trabalha para corrigi-lo e reporta ao líder do teste que ele está resolvido. Mais uma vez, o testador realiza o teste e verifica que ele não foi resolvido. O erro, então, reassume o status de “aberto”;
- com base em sua prioridade ou gravidade, o erro pode ser postergado. A classificação da gravidade pode ser baixa, média, alta ou crítica.

______

**🔁 Assimile**

A intenção do que chamamos de Engenharia de Testes é simples: oferecer entendimento do que é um erro e oferecer formas de encontrá-lo.

______

Por mais que os procedimentos de teste sejam tidos como universais, não há como não os vincular ao modelo de desenvolvimento adotado para a construção do programa que será testado. Os dois modelos – tradicional e ágil – apresentam particularidades no trato do processo de teste, tais como quais testes serão executados e quando.

Vejamos em detalhes como os modelos Cascata e Extreme Programming (XP) conduzem os testes.

# **Modelo Cascata e TDD**

[![](https://ampli-images.s3.amazonaws.com/production/104e793d-b073-4b12-b1f4-f0a053918da1/original)](https://ampli-images.s3.amazonaws.com/production/104e793d-b073-4b12-b1f4-f0a053918da1/original)

Teoricamente, a fase de testes nesta metodologia concentra-se logo após o término da fase de codificação do programa. Na prática, contudo, o que se tem adotado é a revisão dos artefatos criados em cada uma das fases, sejam eles documentos, especificações, projetos ou um programa.

Ao longo dos anos, a aplicação de verificações e validações (nas quais o teste está incluído) apenas no programa executável mostrou-se ineficiente, principalmente por deixar incorreções da especificação dos requisitos propagarem-se pela fase de implementação (PINHEIRO, 2015). Na sequência, abordaremos o já conhecido TDD, meio pelo qual o XP conduz seu processo de teste.

**TDD - Test-Driven Development (Desenvolvimento Guiado pelos Testes)**

Trata-se de um formato de teste muito parecido com o “codificar e testar”, modelo de desenvolvimento no qual não se dá ênfase a outras etapas, senão as de codificar e testar.

_____

**➕ Pesquise mais**

O formato “codificar e testar” é também conhecido como metodologia codifica-corrige. Leia mais sobre o tema nos artigos "[_Metodologias de desenvolvimento de software_](https://marcelocoelhao.wordpress.com/2010/01/06/metodologias-de-desenvolvimento-de-software/)” e “[_Test Driven Development: TDD Simple_](https://www.devmedia.com.br/test-driven-development-tdd-simples-e-pratico/18533)_”._

_____

Para a realização dos testes, o TDD apoia-se no fato de que a descrição dos requisitos – ou as histórias escritas pelo cliente – não constitui documento com excessiva formalidade e detalhamento de funções e que, por esse motivo, o cliente deve acompanhar o processo de codificação e teste. Em tempos passados, o teste era realizado tomando-se como base o código completo, ou quase completo, já que as linguagens de programação dificultavam a execução de apenas partes do programa. Hoje em dia, tecnologias que suportam linguagens orientadas a objeto (como o Java, por exemplo) permitem não só a automatização dos testes – ação tão importante no âmbito do TDD – como também a execução de partes autônomas de um programa, como uma classe, por exemplo.

O teste de parte do código segue-se à sua criação, ou seja, o teste e a integração são feitos logo após sua codificação. Os passos do desenvolvimento guiado pelos testes incluem:

- a seleção de um conjunto de casos de teste;
- a execução do caso de teste. Encontrando-se o defeito, o código deverá ser ajustado. Caso não se encontre defeito, novo conjunto de casos de teste deve ser selecionado e o processo deve ser reiniciado (PINHEIRO, 2015).

_____

**💭 Reflita**

Por que a figura do testador é necessária no processo de testes? Por que os desenvolvedores, eles próprios, não assumem os testes?

Reflita: os testes feitos por desenvolvedores tendem a verificar apenas trechos do código que, provavelmente, não conterão defeitos. Desenvolvedores só conseguem enxergar de 50% a 60% dos casos de teste. O testador, por sua vez, tem perfil diferente. São exploradores, gostam de encontrar problemas, são criativos nas execuções do _software_ e possuem visão das diferentes situações em que o programa pode ser usado (PINHEIRO, 2015).

_____

Esse foi o conteúdo teórico preparado para esta aula. Na parte da aula reservada às questões práticas, trataremos da aplicação de um teste funcional.

_____

**💪 Faça você mesmo**

Sua tarefa é conceber e relatar uma sequência de tratamento do erro encontrado no código, seja por meio de fluxograma, seja por meio de descrição textual. O tratamento deve incluir as ações e seus responsáveis.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)

A afirmação de que a atividade de teste deve ser bem planejada e estruturada antes de ser executada, feita na aula anterior, ainda soa atual aqui. A seleção dos casos de teste foi o primeiro passo tomado pela _XAX-Sooft_ para disciplinar o processo de teste. Agora chegou o momento de efetivamente aplicar o teste funcional, com o cuidado de estabelecer critérios para o tratamento dos erros encontrados e responsáveis por cada etapa do processo.

Como desafio proposto, sua missão então é a de aplicar o teste funcional num dos produtos da empresa, obedecendo aos critérios previamente definidos. Tome por base o cenário descrito na sequência para a resolução do caso. Como as circunstâncias não são as mesmas especificadas na aula anterior, assuma que os casos de teste apropriados para esse teste já foram selecionados.

- A equipe designada para a tarefa conta com um testador, dois desenvolvedores e um líder de desenvolvimento;
- Existem três funções a serem testadas no programa: manutenção de dados do contato, geração de relatório dos clientes mais rentáveis por período e envio automático de mensagem ao cliente aniversariante.

Uma solução possível para esse desafio é a que segue.

Com base nos casos de teste criados, o testador deverá executar o programa e conferir as saídas que cada uma das funções fornece quando acionadas.

Caso um erro seja encontrado pelo testador, ele deverá ser verificado pelo líder do desenvolvimento. Se for constatado que, de fato, se trata de um erro, sua descrição será passada a um dos desenvolvedores, com indicação em qual função ele foi encontrado.

O desenvolvedor procede a correção e repassa a informação de ajuste feito ao líder do desenvolvimento que, por sua vez, realiza nova verificação. Se, na visão do desenvolvedor e de seu líder, o erro não existir mais, nova informação de ajuste feito é emitida, desta vez ao testador, que faz a validação ou não da correção.

Durante o processo, os envolvidos deverão anotar o tempo utilizado em cada correção, em qual função o erro foi encontrado, as ocorrências de não validação do erro e as ocorrências de não validação do ajuste feito.

- Caso o código tenha sido escrito na linguagem Java, este procedimento poderá ser desenvolvido na JUnit, ferramenta gratuita desenvolvida por Erich Gamma e Kent Beck para criação de testes automatizados.

_____

**⚠️ Atenção**

Por causa das suas especificidades, o tempo empenhado nos testes e nas correções varia de função para função.

_____

**📌Lembre-se**

Não se deve assumir que um erro foi corrigido sem que um novo teste seja feito.