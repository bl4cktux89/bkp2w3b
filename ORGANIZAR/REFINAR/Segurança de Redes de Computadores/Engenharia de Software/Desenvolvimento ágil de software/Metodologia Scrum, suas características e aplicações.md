# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/76430b22-c8fa-45be-b10d-d7256c71da7c/original)](https://ampli-images.s3.amazonaws.com/production/76430b22-c8fa-45be-b10d-d7256c71da7c/original)

### **Qual é o foco da aula?**

Nesta aula, você tomará contato com a metodologia ágil _Scrum_, suas práticas se aproximam conceitualmente das práticas do XP e tornam essa metodologia bastante aceita entre as empresas de desenvolvimento de _software_.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- examinar como funciona a metodologia _Scrum_ no desenvolvimento de _software_;
- identificar seus atores e processos;
- analisar como ocorre uma _Sprint_ e como sua tarefa é dimensionada.

**Situação-problema**

Olá, estudante! Chegamos à última aula desta unidade!

A terceira etapa do processo de implantação da metodologia _Extreme Programming_ na _XAX-Sooft_ foi concluída com sucesso. Como forma de introduzir o XP como modelo oficial da empresa, você cuidou da implantação do Desenvolvimento Guiado pelos Testes, Padrões de Codificação, Refatoração e Integração Contínua.

Atualmente, a equipe já cumpre relativamente bem as novas rotinas e a experiência com o modelo ágil tem agradado os dirigentes da _XAX-Sooft_. No entanto, assim como acontece em qualquer processo de desenvolvimento, as práticas do XP precisam passar por maturação e aprimoramento constante. Você sabe que a correta operacionalização do modelo ágil depende, em parte, da contínua reafirmação dos seus valores. No mesmo sentido, a obtenção de bons resultados tem relação estreita com o encantamento que o modelo consegue provocar nos envolvidos e principalmente no cliente.

Está posto, então, seu novo desafio: por meio de documento próprio em que você deverá planejar ações que visem a manutenção e o aprimoramento das práticas do XP. Como consequência direta dessas ações, deve também compor o documento suas sugestões para que a satisfação e o encantamento do cliente sejam garantidos.

Com essa atividade, você poderá aprofundar-se nos conceitos e na correta operacionalização das práticas do XP implantadas pela XAXSooft e ter condições de, no futuro, propor variações, novidades e melhorias na rotina da equipe.

No entanto, o objetivo de aprendizagem desta aula é apresentar a metodologia Scrum, suas práticas e documentos relacionados, a fim de que você conheça e assimile o funcionamento geral do Scrum e seja capaz de estabelecer comparações com o XP.

Assim como o XP, ela tem sido utilizada em boa parte das empresas que decidiram adotar o modelo ágil de desenvolvimento. Com esse conhecimento, você estará apto a fazer comparações entre as duas metodologias e a realizar escolhas com toda autoridade.

Em outras palavras, nesta aula você estará concluindo a aquisição da competência técnica planejada para esta unidade, que inclui conhecimento das principais metodologias ágeis de desenvolvimento e habilidade em contrapô-las com a metodologia tradicional. Tudo isso sem perder de vista, é claro, a competência geral proposta para o curso, que é conhecer as principais metodologias de desenvolvimento de _software_, normas de qualidade e processos de teste de _software_.

Bom trabalho e siga em frente com os estudos.

# **Perfil dos atores**

[![](https://ampli-images.s3.amazonaws.com/production/b30d3360-f9cb-4a26-9fe5-360e783e189c/original)](https://ampli-images.s3.amazonaws.com/production/b30d3360-f9cb-4a26-9fe5-360e783e189c/original)

Para que o _Scrum_ seja devidamente apresentado a você, começaremos pela descrição do perfil dos seus atores. É importante destacar que, embora exista versão coerente na língua portuguesa para os nomes utilizados pela metodologia, manteremos os originais na língua inglesa.

Pois bem, três figuras importantes fazem parte do _Scrum_:

1. _Scrum Team_: trata-se da equipe de desenvolvimento. A exemplo do XP, aqui também a quantidade de elementos da equipe responsável por um projeto gira em torno de 8 a 10 pessoas. Outra semelhança notável é a falta de especialização entre seus componentes: não há separação clara entre, por exemplo, a funções de analista, programador e projetista, pois todos colaboram para o desenvolvimento do produto em conjunto (WAZLAWICK, 2013).
2. _Product Owner_: literalmente, o dono do produto. Ele é responsável pelo projeto e por determinar quais funcionalidades serão implementadas em cada Sprint. A propósito, Sprint é o nome que o Scrum dá a cada período em que a equipe se reúne para, de ato, construir o produto. O contato direto com o cliente é mais uma atribuição importante do _Product Owner_.
3. _Scrum Master_: por conhecer bem a metodologia ele age como um facilitador no projeto e cuida para que as práticas do Scrum sejam seguidas. Não se trata, no entanto, de um gerente no sentido tradicional do termo. Pode ser um membro qualquer da equipe, preferencialmente bem articulado e experiente.

# **Documentos do Scrum**

[![](https://ampli-images.s3.amazonaws.com/production/09bf51a5-ee8d-443f-98e9-eed75f57a394/original)](https://ampli-images.s3.amazonaws.com/production/09bf51a5-ee8d-443f-98e9-eed75f57a394/original)

O _Scrum_, a exemplo do XP, também se desenvolve com base em práticas e documentos relacionados a elas. Na sequência você irá conhecer alguns desses documentos.

- _Product Backlog_: é um documento indispensável no modelo. Ele é criado pelo Scrum Master e contém as funcionalidades a serem implementadas no projeto. Você deve ter percebido que a palavra “todas” não antecedeu a palavra “funcionalidades” nesta última frase. Isso tem um motivo: o _Product Backlog_ não precisa ser completo no início do projeto. É recomendável que o documento seja iniciado apenas com as funcionalidades mais evidentes. Depois, à medida que o projeto avança, ele deverá conter novas funcionalidades que forem sendo descobertas.

_____

**📝 Exemplificando**

Veja um bom exemplo de Product Backlog (WAZLAWICK, 2013):

[![](https://ampli-images.s3.amazonaws.com/production/9bbe4e47-1b34-40bd-8191-e2be090a4688/original)](https://ampli-images.s3.amazonaws.com/production/9bbe4e47-1b34-40bd-8191-e2be090a4688/original)

Que tal uma olhada mais cuidadosa nos campos que o _Product Backlog_ contém? Vamos a eles (WAZLAWICK, 2013):

1. _Id_: trata-se de um contador cujo objetivo é não deixar que a equipe perca a trilha das histórias do cliente em caso de mudança de nome ou descrição. Pense nele como um identificador numérico da funcionalidade.
2. nome: representa a história do cliente em uma expressão fácil de ser lembrada.
3. _Imp_: este campo é bastante útil e interessante, já que expressa a importância que o cliente dá aquela funcionalidade. A equipe pode fazer outras convenções, mas geralmente números mais altos representam importâncias maiores.
4. PH: significa Pontos de Histórias e é a tradução da estimativa de esforço para transformar a história em _software_. Você se lembra de como a equipe do XP planejava o desenvolvimento das funcionalidades? Pois bem, o princípio aqui é o mesmo. Um ponto de história pode ser definido como o esforço de desenvolvimento de uma pessoa durante um dia ideal de trabalho, sem interrupções.
5. como demonstrar: este campo descreve o que deve ser possível fazer para que a história possa ser de fato implementada. Esta descrição deve ser de tal maneira bem detalhada a ponto de ser usada como um teste possível para a história.
6. notas: campo livre destinado às observações feitas pela equipe.

_____

**💭 Reflita**

Como você determina o grau de importância da funcionalidade? A observação das reações do cliente quando trata dela, a quantidade de vezes que é repetida por ele e a ênfase dada àquela característica do sistema revelam sua importância ao cliente.

Naturalmente que nessa avaliação devem também ser considerados fatores técnicos e funcionalidades cuja existência justificam o produto, estes também têm alto grau de importância no projeto.

_____

Os campos do _Product Backlog_ aqui demonstrados não são os únicos viáveis. Você e sua equipe podem, a critério de ambos, estabelecer outros campos ou níveis de informações mais aprofundados, tudo em nome da boa comunicação e do perfeito entendimento do problema.

_____

**➕ Pesquise mais**

Quer saber mais sobre o Product Backlog? Leia os artigos sugeridos abaixo:

1. “[The product backlog: your ultimate to-do list](https://www.atlassian.com/agile/scrum/backlogs)”;
2. “[_Product Backlog_](http://www.desenvolvimentoagil.com.br/scrum/product_backlog)”.

# **A Sprint**

[![](https://ampli-images.s3.amazonaws.com/production/6a1c5ba9-267c-4ce4-a110-a3600c62b4d1/original)](https://ampli-images.s3.amazonaws.com/production/6a1c5ba9-267c-4ce4-a110-a3600c62b4d1/original)

A prática que mais destaca o Scrum das outras metodologias ágeis é o _Sprint_. Se você é fã de atletismo ou de ciclismo certamente já relacionou o termo a estas modalidades. No Atletismo, o _sprint_ é momento da corrida em que o competidor aumenta a velocidade para chegar na frente dos outros competidores.

No _Scrum_, é o momento de esforço concentrado – ou um ciclo de desenvolvimento em que determinadas funcionalidades viram programa. Conforme você já estudou, quem determina quais são essas funcionalidades é o _Product Owner_.

Ele as prioriza e as registra durante o planejamento do ciclo, em uma reunião chamada _Sprint Planning_ _Meeting_ e em um documento chamado _Sprint Backlog_. Tal documento nada mais é do que a lista dos itens extraídos do Product Backlog que serão desenvolvidos naquele determinado _Sprint_. Complicado?

Pense então numa lista com as funcionalidades do produto e numa outra lista com itens – escolhidos e extraídos da primeira – que serão implementados na próxima vez em que os desenvolvedores se reunirem para esse fim. Essa é a relação entre _Product Backlog_ e _Sprint Backlog_.

É normal e desejável que essa segunda lista, embora contendo itens extraídos da primeira, os apresente com termos mais técnicos e voltados à maneira como a equipe irá construí-los.

Cada _Sprint_ dura de uma a quatro semanas, dependendo da complexidade e da quantidade das funcionalidades a serem criadas. Durante esse período, o _Product Owner_ não irá levar à equipe outras funcionalidades. Ao contrário, as registrará para o próximo _Sprint_.

Bem, até o momento foi apresentada a você a seguinte rotina: com base nas histórias do cliente, o _Product Owner_ cria uma lista de funcionalidades do sistema chamada _Product Backlog_. Quando a equipe se reúne para o ciclo de desenvolvimento (_Sprint_), o _Product Owner_ cria a lista de funcionalidades que serão desenvolvidas naquele ciclo.

Essa lista é derivada da primeira, leva o nome de _Sprint Backlog_ e é criada durante a reunião chamada _Sprint Planning Meeting_. O _Sprint_ dura poucas semanas e, enquanto acontece, nenhuma outra funcionalidade é enviada à equipe. Interessante, não acha? Mas ainda há um pouco mais a conhecer sobre o _Sprint_.

______

**➕ Pesquise mais**

A [_Sprint Planning Meeting_](http://www.desenvolvimentoagil.com.br/scrum/sprint_planning_meeting) é a reunião em que se planeja o próximo _Sprint_ e se decidem as funcionalidades que serão implementadas naquele ciclo. Leia o artigo indicado para compreender mais sobre o assunto.

# **As tarefas da Sprint**

[![](https://ampli-images.s3.amazonaws.com/production/35220da7-14ff-4e49-81d1-288d6580b036/original)](https://ampli-images.s3.amazonaws.com/production/35220da7-14ff-4e49-81d1-288d6580b036/original)

À medida que o _Sprint_ avança e as funções do sistema vão sendo criadas, cabe ao _Product Owner_ manter atualizada a lista de itens daquele ciclo. As tarefas já concluídas e aquelas ainda a serem feitas são mostradas em um quadro atualizado diariamente e à vista de todos. A cada dia pode-se avaliar o andamento das atividades, contando a quantidade de tarefas a fazer e a quantidade de tarefas terminadas, o que vai produzir um diagrama chamado _Sprint Burndown_ (WAZLAWICK, 2013).

Se você considerar que a quantidade de trabalho já feita e a quantidade de trabalho a ser feita geram, cada um, uma linha neste diagrama, é natural pensar que a situação ideal ocorre quando o encontro das linhas se dá no centro do gráfico. Quer entender melhor? Observe a figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/0967b4e5-017c-4121-80c9-1b405e81ee43/original)](https://ampli-images.s3.amazonaws.com/production/0967b4e5-017c-4121-80c9-1b405e81ee43/original)

Relação ideal entre tarefas. Fonte: Wazlawick (2013, p. 59).

Neste caso, o número de tarefas feitas cresce de forma sustentável em função do tempo, enquanto a quantidade de tarefas a serem feitas cai na mesma taxa.

Ao tomarmos familiaridade com a disposição da linha de “Tarefas por Fazer” no _Sprint Burndown_, seremos capazes de identificar alguns tipos de comportamentos da equipe (MAR, 2006).

Como exemplo, a figura abaixo mostra o comportamento de uma equipe que conseguiu entender as funcionalidades depois de passada a maior parte do _Sprint_. Essa curva pode indicar perfil de iniciante nos membros da equipe.

[![](https://ampli-images.s3.amazonaws.com/production/f6066389-7be1-435b-94bc-94bc4f0ed39d/original)](https://ampli-images.s3.amazonaws.com/production/f6066389-7be1-435b-94bc-94bc4f0ed39d/original)

Comportamento típico de equipe iniciante. Fonte: elaborada pelo autor.

Terminado o _Sprint_, a equipe deve realizar nova reunião, esta chamada de _Sprint Review Meeting_, na qual será avaliado o produto gerado pelo _Sprint_.

______

**📌Lembre-se**

De maneira geral, o modelo ágil recomenda que seja entregue ao cliente o mais cedo possível um programa executável para que ele possa usar, testar e aprender mais sobre o que está sendo produzido. O Scrum leva a sério esse princípio e entrega ao cliente parte do programa após o término de cada ciclo de desenvolvimento.

______

O _Scrum_, a exemplo do XP, também prevê a realização diária de reunião na qual o dia atual é planejado e o dia anterior é revisado. A recomendação é que este encontro, chamado de _Daily Scrum_ – também seja feito com seus participantes em pé e que dure apenas alguns minutos.

# **Referências bibliográficas**

[![](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)

HIBBS, C.; JEWETT, S.; SULLIVAN, M. _**The Art of Lean Software Development**_: A Practical and Incremental Approach, 1. ed. O’Reilly Media, Inc., CA. 2009.

PRESSMAN, R. S. **Engenharia de** _**software**_. São Paulo: Pearson Prentice Hall, 2009. 1056 p.

PAULA FILHO, W. de P. **Engenharia de** _**software**_: fundamentos, métodos e padrões. 2. ed. Rio de Janeiro: Livros Técnicos e Científicos, 2005. 602 p.

REZENDE, D. A. **Engenharia de** _**software**_ **e sistemas de informação**. 3. ed. rev. e ampl. Rio de Janeiro: Brasport, 2005.

SCHACH, S. **Engenharia de** _**software**_: os paradigmas clássico e orientado a objetos. 7. ed. São Paulo: McGraw-Hill, 2008.

SOMMERVILLE, I. **Engenharia de** _**software**_. 8. ed. São Paulo: Addison Wesley, 2008. 592 p.

TELES, V. M. _**Extreme Programming**_: aprenda como encantar seus usuários desenvolvendo _software_ com agilidade e alta qualidade. São Paulo: Novatec, 2004. 316 p.

WAZLAWICK, R. S. **Engenharia de** _**software**_: conceitos e práticas. 1. ed. Rio de Janeiro: Elsiever, 2013.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/add8528f-cdc3-4eb4-8b7c-dd722eb0c857/original)](https://ampli-images.s3.amazonaws.com/production/add8528f-cdc3-4eb4-8b7c-dd722eb0c857/original)

Todas as práticas do XP que a _XAX-Sooft_ planejou implantar já estão fazendo parte da rotina das equipes de desenvolvimento. Num primeiro momento, as práticas mais diretamente relacionadas à comunicação e ao _feedback_ tomaram seu lugar no cotidiano dos desenvolvedores e, à medida que experimentavam maturação, outras relacionadas ao código do programa, testes e integração foram também sendo introduzidas.

As coisas andam bem, mas você entende que elas ainda podem ser melhoradas e que as práticas implantadas podem contribuir ainda mais com o sucesso da sua empresa. Aprimorar os processos internos tem relação quase direta com o encantamento que o XP se propõe a provocar nos clientes. E é exatamente isso que você quer para a XAXSooft.

Novamente você deve recorrer ao que foi proposto na introdução para retomar o desafio desta aula. Em um relatório você poderá planejar ações que impliquem manutenção e aprimoramento das práticas do XP. Como desdobramento direto dessas ações, o estreitamento da relação com os clientes deveria também ser buscado. Deste ponto em diante será apresentada uma forma possível de compor esse relatório.

1. Ao menos dois membros previamente escolhidos da equipe deverão ficar responsáveis pelo treinamento dos novos desenvolvedores que venham a ingressar na _XAX-Sooft_. O sucesso das práticas não pode estar relacionado à pessoa que as realiza, mas à cultura implantada na empresa.
2. Em intervalos regulares, a direção da _XAX-Sooft_ (ou alguém designado por ela) deverá colher percepções e sugestões da equipe sobre sua rotina. Com esta providência, espera-se que eventuais insatisfações em relação ao trabalho venham à tona, sejam sanadas na medida do possível e não se tornem pretexto para descumprimento das práticas implantadas.
3. Deve ser disponibilizado um repositório de experiências e melhores práticas, que possa ter seu conteúdo editado por todos. Assim, a comunicação terá chance de ser aprimorada e experiências vividas no modelo poderão ser facilmente compartilhadas.
4. Por fim, a parte do relatório que aborda o encantamento do cliente deve prever meios de se estabelecer relacionamento duradouro e profícuo com ele. As entregas regulares e corretamente testadas, a cobrança de valor justo, o estabelecimento de regras claras desde o início do projeto e o definitivo posicionamento do cliente como centro do projeto são ótimas providências para que ele continue a encomendar novos projetos e a chamá-lo para aprimorar os já entregues, o que gera valor à empresa.

_____

⚠️ **Atenção**

Não se pode esperar que um cliente, que eventualmente já tenha participado de projetos no modelo tradicional, incorpore imediatamente o modo de operação do modelo ágil. Nas primeiras experiências, ele precisará de motivação e de confiança no trabalho da equipe e de seus gestores.

______

**📌Lembre-se**

O encantamento do cliente gera fidelização. Leia as matérias a seguir: “[_Como a Revenda de TI Pode Fidelizar e Cuidar Melhor dos Clientes_](https://blogbrasil.comstor.com/como-a-sua-revenda-de-ti-pode-fidelizar-e-cuidar-melhor-dos-clientes)” e “[_5 dicas para atender bem o cliente_](https://administradores.com.br/artigos/5-dicas-para-atender-bem-o-cliente)”