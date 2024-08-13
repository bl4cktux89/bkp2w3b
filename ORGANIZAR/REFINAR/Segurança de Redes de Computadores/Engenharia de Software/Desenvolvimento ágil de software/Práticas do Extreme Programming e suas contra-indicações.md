# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/9f197311-642e-4d9a-aae6-ca99314cf850/original)](https://ampli-images.s3.amazonaws.com/production/9f197311-642e-4d9a-aae6-ca99314cf850/original)

### **Qual é o foco da aula?**

Nesta aula, serão tratadas outras práticas do XP, tão importantes quanto as estudadas na aula anterior.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- esclarecer os princípios do desenvolvimento guiado por testes;
- examinar como ocorre a integração contínua e seus padrões;
- discutir o que é e como ocorre a refatoração.

**Situação-problema**

Olá, estudante! Que bom te encontrar aqui.

A segunda etapa do processo de implantação da metodologia _Extreme Programming_ na _XAX-Sooft_ foi concluída. Ela previa a implantação de práticas do XP relacionadas à comunicação e visava trazer o cliente para o centro do processo e aprimorar o relacionamento entre membros da equipe.

Sua experiência em identificar necessidades de mudanças no processo de desenvolvimento e efetivá-las foi decisiva para este início de transição entre o modelo tradicional e o modelo ágil. No entanto, o trabalho ainda não está terminado!

Sua missão agora é dar continuidade ao processo de mudança, planejando e realizando a introdução principalmente das práticas do XP voltadas à Integração Contínua e ao Desenvolvimento Guiado pelos Testes. Como trabalho adicional – mas não menos importante – você deverá também iniciar as práticas de refatoração e padrão de codificação.

Além disso, você deverá explicitar as contraindicações da metodologia XP, ao destacar suas vulnerabilidades e pontos de deficiência.

Assim, você poderá aprimorar seus conhecimentos sobre o XP e aumentar sua habilidade em compará-la com a metodologia tradicional. Novamente, para que você se saia bem nesse desafio, é preciso que se empenhe na compreensão da teoria desenvolvida na aula, na qual as práticas serão abordadas.

Em resumo, nesta etapa do desafio você deve planejar e executar a implantação das práticas conhecidas como Integração Contínua, Desenvolvimento Guiado pelos Testes, Refatoração e Padrão de Codificação, por meio de relatório, com isso atendemos ao objetivo de aprendizagem desta aula que é: fornecer subsídios para que estudantes possam planejar a introdução de práticas do XP relacionadas à integração contínua e testes.

Desde já, bons estudos!

# **Desenvolvimento guiado pelos testes**

[![](https://ampli-images.s3.amazonaws.com/production/9323b47d-3583-4853-ae9c-18bbc2d42ce4/original)](https://ampli-images.s3.amazonaws.com/production/9323b47d-3583-4853-ae9c-18bbc2d42ce4/original)

O Extreme Programming adota uma série de práticas que o tornam um meio moderno, ágil e inovador de se vencer o processo de criação de um programa. Você estudou as práticas de Cliente Presente, Jogo do Planejamento, Programação em Par, Código Coletivo, _Stand up Meeting_ e Metáforas e descobriu que em todas elas há pelo menos uma quebra de paradigma em relação ao modelo tradicional. Afinal, nesse modelo não se coloca o cliente no centro do processo de desenvolvimento; os requisitos são levantados e registrados pela própria equipe, a construção de uma parte do programa é feita por uma única pessoa de cada vez e o código não é de propriedade coletiva.

Além disso, o modelo tradicional não prevê reuniões diárias (embora não impeça que sejam feitas) e não faz uso de metáforas para aprimorar a comunicação entre os membros da equipe.

Antes de entrarmos especificamente no assunto de desenvolvimento guiado pelos testes , vale conceituar dois termos importantes no contexto (WAZLAWICK, 2013):

- **teste de unidad**e: este teste consiste em verificar se um componente individual do _software_ (uma unidade) foi implementado corretamente. Este componente pode ser uma classe, um método ou um pacote de funções e geralmente está isolado do sistema do qual faz parte. O desenvolvimento guiado pelos testes recomenda, inclusive, que antes de o programador desenvolver uma unidade de _software_, ele deve gerar o seu driver de teste, que é um programa que obtém ou gera um conjunto de dados que serão usados para testar o componente que ainda será desenvolvido;
- **teste de aceitação**: este teste é realizado pelo cliente, que utilizará a interface final do sistema. A aplicação do teste de aceitação visa a validar o _software_ em relação aos requisitos e não mais em relação a verificação de defeitos.

Explicados os conceitos, vamos ao nosso assunto principal.

Originalmente identificada como Test-Driven Development (TDD), a adoção desta prática tem como objetivo a identificação e correção de falhas durante o desenvolvimento, não apenas ao final dele.

O processo de teste, quando aplicado da maneira tradicional, tende a ser difícil, especialmente quando você está testando seu próprio código. Escrever um teste para que ele falhe pode ser desencorajador. É muito fácil querer chegar logo ao final de um teste, esperando que tudo funcione corretamente (O’REILLY, 2009).

O **desenvolvimento guiado pelos testes** é diferente. Para que a condução desta prática seja feita corretamente e produza bons resultados, o XP propõe algumas regras (WAZLAWICK, 2013):

**a)** todo código deve passar pelos testes de unidade antes de ser entregue: esta providência ajuda a assegurar que sua funcionalidade seja implementada corretamente. Os testes de unidade também favorecem a refatoração – que será abordada adiante nesta aula – porque protegem o código de mudanças indesejadas de funcionalidade. A introdução de uma nova funcionalidade deverá levar à adição de outros testes ao teste de unidade específico;

**b)** quando um erro de funcionalidade é encontrado, testes são criados: um erro de funcionalidade identificado exige que testes de aceitação sejam criados. Desta forma, o cliente explica com clareza aos desenvolvedores o que eles esperam que seja modificado;

**c)** testes de aceitação são executados com frequência e os resultados são publicados. Os testes de aceitação são criados a partir das histórias do cliente. Durante uma iteração, as histórias selecionadas para implementação serão traduzidas em testes de aceitação.

# **Integração contínua**

[![](https://ampli-images.s3.amazonaws.com/production/4a50f469-f7e1-455c-92d4-caf8f1ba161c/original)](https://ampli-images.s3.amazonaws.com/production/4a50f469-f7e1-455c-92d4-caf8f1ba161c/original)

Conforme tratamos na unidade 1, a integração de um _software_ refere-se ao momento em que ocorre a união dos módulos criados separadamente, de modo a se obter um sistema único. Não há nada de errado com essa abordagem, mas aqui neste contexto a prática será tratada de forma ligeiramente diferente. Prossigamos.

Na forma em que é realizada no âmbito do modelo tradicional de desenvolvimento, é comum que os desenvolvedores convencionem interfaces, de modo que possam fazer a integração em momento futuro (TELES, 2004).

No entanto, erros na integração serão frequentes caso os padrões definidos para as interfaces (assinaturas de métodos, por exemplo) não sejam respeitados ou assimilados pela equipe. Quanto maior o intervalo entre uma integração e outra, mais a equipe terá dificuldades em fazer o sistema rodar e os testes funcionarem (TELES, 2004).

O XP adota a prática da [integração contínua](http://www.desenvolvimentoagil.com.br/xp/praticas/integracao), que consiste em integrar o trabalho diversas vezes ao dia, assegurando que a base de código permaneça consistente ao final de cada integração (TELES, 2006).

A primeira providência que você deve tomar para promover a integração contínua é criar um repositório de programas. O sistema em construção deve estar alocado em um repositório comum, disponível para todos os pares de programadores (o código é coletivo no XP, lembra-se?) e cada alteração aplicada nesse sistema deve ser controlada por um sistema de controle de versões.

O _Microsoft Visual SourceSafe_ e o _CVS_ (do inglês _Concurrent Version System_) são ótimos produtos de mercado, assim como o _Subversion_. Este último produto é gratuito e de fonte aberta, capaz de controlar arquivos e diretórios de programas, bem como as alterações feitas neles ao longo do tempo. Ele permite que você recupere versões antigas de seus dados ou examine o histórico de como os programas foram alterados.

O _Subversion_ pode operar entre diversas redes, o que permite que seja usado por pessoas em diferentes computadores. Desta forma, a possibilidade de várias pessoas modificarem e gerenciarem o mesmo conjunto de dados de seus próprios locais fomenta a colaboração entre elas.

_____

**➕ Pesquise mais**

Para que sua operação seja possível, alguns comandos devem ser usados. Eis alguns exemplos no artigo “[_Version Control with Subversion_](http://svnbook.red-bean.com/en/1.7/svn-book.pdf)_”_

_____

[![](https://ampli-images.s3.amazonaws.com/production/afe7a339-1e6e-44ab-8d27-a629a82877f0/original)](https://ampli-images.s3.amazonaws.com/production/afe7a339-1e6e-44ab-8d27-a629a82877f0/original)

______

**🔁 Assimile**

Entenda repositórios de código como uma máquina que centraliza todos os arquivos referentes ao projeto em andamento e que contém sistema de controle de versão.

Diversas versões do sistema ficarão gravadas nesse repositório e, no caso de a versão atual apresentar problemas, a anterior será recuperada. Todos os desenvolvedores deverão ter acesso a esse repositório.

______

Durante o desenvolvimento do produto, será comum que dois pares de programadores acessem simultaneamente um arquivo para alterá-lo.

Através do recurso do checkout, um par de programadores pode tornar o arquivo disponível para si em modo de leitura e alteração e impossibilitar a gravação para todo o resto da equipe. Quando sua tarefa chega ao fim, o sistema deverá integrar o código recém-construído ao repositório.

Neste contexto, uma outra ferramenta digna de sua atenção é o Eclipse. Trata-se de um ambiente de desenvolvimento gratuito e completo para Java, embora suporte também outras linguagens.

_____

**➕ Pesquise mais**

Quer conhecê-lo melhor? Acesso o site [Eclipse.org](https://www.eclipse.org/) e leia o artigo _“_[_Conhecendo o Eclipse - Uma apresentação detalhada da IDE_](https://www.devmedia.com.br/conhecendo-o-eclipse-uma-apresentacao-detalhada-da-ide/25589)”.

_____

**📝 Exemplificando**

Um bom exemplo de integração contínua pode ser dado por meio da situação em que dois programadores estejam criando uma calculadora em Java usando o ambiente de desenvolvimento Eclipse.

Cada par deverá contar com uma instância diferente do Eclipse em execução e duas áreas de trabalhos diferentes devem ser criadas. Com projetos e diretórios também separados, ambos começam a dar contribuições no projeto.

O primeiro par executa aprimoramentos na classe que realiza a multiplicação e o segundo altera o código da classe da divisão. Implementadas e testadas as alterações, basta que atualizem seus códigos no repositório.

Ao fazerem pequenas e constantes integrações durante o dia, o esforço de criação do sistema tenderá a ser menor e os inevitáveis erros tenderão a ser menos graves e tratados com mais facilidade.

# **Padrões de codificação, características, manutenção e dificuldades**

[![](https://ampli-images.s3.amazonaws.com/production/607f2cb9-5499-47b4-b794-7f554d2c27c9/original)](https://ampli-images.s3.amazonaws.com/production/607f2cb9-5499-47b4-b794-7f554d2c27c9/original)

O fomento da comunicação num ambiente de XP também se dá através do código dos programas. A equipe deve se comunicar de forma clara através do código e, por isso, o XP sugere a adoção de **padrões de codificação**.

Diferentes programadores têm diferentes estilos de programação, que podem dificultar a compreensão do código por parte dos membros da equipe. A adoção de um mesmo estilo de programação pode evitar essa dificuldade (TELES, 2004).

Deve-se adotar um padrão fácil e de simples compreensão. Confira algumas dicas que você pode usar na construção de um padrão, as **características** (TELES, 2004):

- endentação: mesma largura na tabulação e mesmo posicionamento de chaves (abertura e fechamento de bloco);
- letras maiúsculas e minúsculas: deve ser mantida a consistência com a caixa da letra (alta ou baixa). Java, por exemplo, tem uma padronização bem definida de maiúsculas e minúsculas;
- comentários: evite comentários no código. Código simples transmite mais a mensagem do que quaisquer comentários;
- nomes de identificadores: use nomes que comuniquem a ideia. Se preciso, use nomes longos. Padrões para nomes de tabelas também devem ser seguidos. É essencial que a equipe consiga descrever coisas similares com nomes similares.

Quando alguém identifica um código fora do padrão, deve-se alertar a equipe que o padrão não foi respeitado e orientar sobre a forma de **manter o padrão**.

Normalmente, exceções ao padrão só ocorrem no início do projeto. Enquanto a equipe estiver no processo de adaptação, você pode achar interessante publicar as regras do padrão em local visível da sala de desenvolvimento, a fim de que todos possam consultá-las.

Não são descartados ajustes no padrão para que ele se aproxime daquilo que os programadores estão mais habituados.

Pode haver desconforto quando um programador precisa mudar seu padrão pessoal. Alterações podem causar resistências, ou seja, **dificuldades na adoção de um padrão**. A equipe deve negociar e entrar em acordo sobre qual padrão adotar.

_____

**💭 Reflita**

Será que o formato de um padrão de codificação é, de fato, menos relevante do que sua própria adoção? Em outras palavras, será que mais vale adotar um formato não tão claro do que nenhum formato?

# **Refatoração (Refactoring)**

[![](https://ampli-images.s3.amazonaws.com/production/576a7335-df62-4e8b-9b33-a4e17c026e2b/original)](https://ampli-images.s3.amazonaws.com/production/576a7335-df62-4e8b-9b33-a4e17c026e2b/original)

Imagine que você tenha empreendido bastante esforço e conhecimento para criar um programa. Depois de um tempo considerável, ele está funcionando muito bem e executando com perfeição suas funções. No entanto, seu gerente ainda não está satisfeito: agora ele deseja que você altere seu código, apenas para melhorar a escrita e legibilidade, sem que isso implique mudança alguma na lógica implementada e ou no funcionamento do programa.

Arriscado, não acha? Pois essa é justamente a ideia da refatoração ou, como usualmente dito em nosso meio, do _refactoring_.

Refatoração é uma palavra sofisticada usada para identificar a melhoria na escrita de código já criado, sem que isso acarrete alterações em seu comportamento (O’REILLY, 2009).

A necessidade de se refatorar um código não é criação do XP, mas foi alçada a uma de suas práticas pela sua importância no contexto do pensamento ágil.

No âmbito de qualquer modelo de desenvolvimento que se use, um código mal formulado poderá gerar dificuldades para quem um dia precisar modificá-lo ou simplesmente compreendê-lo. O código deve estar preparado para receber manutenções corretivas, evolutivas, preventivas ou adaptativas (TELES, 2004).

_____

**➕ Pesquise mais**

Quer conhecer alguns mitos sobre a refatoração? Leia “[_Esclarecendo os Equívocos Mais Comuns Sobre Refatoração_](https://www.infoq.com/br/articles/RefactoringMyths/)”, um excelente artigo que trata do tema.

_____

A refatoração está ligada ao código coletivo e à implantação de padrões de codificação. Se a ideia é que todos tenham acesso ao código, que ele seja padronizado e ofereça facilidade em sua leitura.

A boa prática indica que o código deve ser refatorado regularmente. Após a execução de um teste, refatore.

Após concluir uma tarefa ou uma função, refatore o código novo. Elimine repetições de código, quebre métodos e funções em partes menores, torne mais claros nomes de variáveis e métodos e, finalmente, deixe o código mais fácil de entender e de ser modificado (O’REILLY, 2009).

______

**📌Lembre-se**

A refatoração, se mal aplicada, também pode fazer o código parar de funcionar. Não mexer no código significa não acrescentar mais um risco, contudo significa também manter no sistema risco potencialmente maior de ser mal compreendido e de ter a manutenção dificultada.

______

Para minimizar riscos, deve-se conhecer bem as técnicas de refatoração e executar testes de unidade após sua execução. Após a refatoração, o desenvolvedor pode ficar à vontade para adicionar ou alterar funcionalidades (TELLES, 2004).

_____

**💪 Faça você mesmo**

Para praticar o que você sabe sobre refatoração e padrões de codificação, tome um programa do qual você tenha o código-fonte, refatore-o e coloque o código no padrão recomendado para aquela linguagem. Lembre-se: nenhuma funcionalidade deverá ser alterada, tampouco seu funcionamento.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/add8528f-cdc3-4eb4-8b7c-dd722eb0c857/original)](https://ampli-images.s3.amazonaws.com/production/add8528f-cdc3-4eb4-8b7c-dd722eb0c857/original)

As práticas do XP mais diretamente relacionadas à comunicação e feedback foram implantadas recentemente na _XAX-Sooft_ e estão caindo no gosto da equipe. Com uma ou outra necessidade de adaptação, cada uma delas foi aos poucos introduzida no cotidiano da equipe e os primeiros sinais positivos da mudança começam a aparecer.

As reuniões diárias têm melhorado a comunicação entre a equipe e a tornado mais coesa. A adoção da programação em par e do código coletivo dão sinais de terem sido ótimas providências para melhorar a qualidade do código e das funcionalidades por ele criadas. Agora a maioria dos erros cometidos na programação são descobertos no ato e a tendência à sua propagação tem diminuído consideravelmente.

E, claro, não podemos nos esquecer do esforço que a _XAX-Sooft_ tem empreendido para trazer o cliente para perto do processo de desenvolvimento. É com boa constância que a equipe tem chamado seu cliente para usar partes prontas do código e opinar sobre necessidades de mudanças pontuais no rumo da criação do produto.

Essa participação tem sanado, quase que em tempo real, as dúvidas da equipe e evitado a introdução de funcionalidades equivocadas. Enfim, seu trabalho até aqui tem se mostrado competente e tem gerado bons resultados.

No entanto, você ainda precisa implantar algumas outras práticas do XP para que sua utilização esteja muito perto da plenitude.

No início da aula foi proposto a você dar continuidade ao processo de mudança, planejando e realizando a introdução da Integração Contínua, do Desenvolvimento Guiado pelos Testes, da Refatoração e de um

Padrão de Codificação.

Novamente trazemos neste ponto uma abordagem possível para a criação desse relatório:

1. caso ainda não exista, um repositório único dos arquivos de programa do projeto deve ser criado.
2. logo em seguida, deve ser providenciada a implantação de _software_ de controle de versão. Com isso, a integração contínua estará apta a ser implantada.
3. para sua efetivação, haverá necessidade de orientar a equipe para que a integração seja feita várias vezes ao dia. Para que a prática do Desenvolvimento Guiado pelos Testes possa ser efetivada, você deverá orientar os desenvolvedores que desenvolvam e apliquem testes automatizados de unidade. A geração dos testes de unidade deve preceder a criação de cada classe.
4. para a implantação da refatoração, você deverá estipular a periodicidade de sua aplicação e as ocasiões em que ela será aplicada.
5. por fim, um padrão de codificação deve ser escolhido e divulgado à equipe. A escolha deverá levar em conta eventual conjunto registrado de boas práticas indicadas pela linguagem de programação utilizada.

_____

**⚠️ Atenção**

Erros na codificação descobertos prematuramente pouparão o tempo da equipe no momento dos testes e da integração.

______

**📌Lembre-se**

O planejamento é indispensável num processo de mudança. A preparação prévia para a mudança inclui a divulgação das práticas à equipe e o estabelecimento de métodos, prazos e objetivos. Boa leitura sobre o tema encontra-se em na matéria “[_O que é Planejamento_](https://www.significados.com.br/planejamento/)”.