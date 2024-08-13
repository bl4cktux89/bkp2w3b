# **Introdução da unidade**

[![](https://ampli-images.s3.amazonaws.com/production/4c43208a-a8c2-4e84-88af-0a07cd4a393a/original)](https://ampli-images.s3.amazonaws.com/production/4c43208a-a8c2-4e84-88af-0a07cd4a393a/original)

### **Objetivos da Unidade**

Ao longo desta Unidade, você irá:

- examinar os métodos ágeis e suas características;
- contrastar os modelos tradicional e o ágil;
- identificar os valores e práticas das metodologias XP (Extreme Programming), Scrum e FDD (Feature-Driven Development).

### **Introdução da Unidade**

Olá, estudante! Iniciamos a segunda unidade do curso de Engenharia de _software_.

Foi durante a primeira parte dos estudos que tivemos a oportunidade de estruturar os meios de produção de _software_ da _XAX-Sooft_ e transformá-la em uma empresa organizada do ponto de vista metodológico.

Por conta de sua implantação descomplicada, a metodologia em cascata foi escolhida e, de certa forma, cumpriu seu papel de conferir ordem a um processo até então caótico.

Acontece, no entanto, que a possibilidade de se organizar uma rotina de desenvolvimento está longe de ficar restrita a uma só metodologia.

Além disso, por mais conhecido e utilizado que seja, o meio tradicional apresenta falhas graves na comunicação com o cliente e períodos excessivamente longos entre a produção e validação dos produtos entregues.

Pois bem, chegou o momento de conhecermos algumas metodologias mais modernas e ágeis de desenvolvimento de _software_. Elas reúnem segmentos bem-sucedidos das metodologias mais antigas, suprimem hábitos ineficientes e incorporam práticas que dão agilidade ao processo, preveem interação constante entre cliente e equipe, aprimoram métodos de teste e, enfim, tornam mais viável e seguro o caminho até um produto de boa qualidade.

Vale a pena, antes de tudo, resgatarmos a competência geral e introduzirmos novas competências e objetivos desta unidade. Em aspectos gerais, nosso estudo visa a apresentar um conteúdo que permitirá a você conhecer as principais metodologias de desenvolvimento de _software_, normas de qualidade e processos de teste de _software_.

Em especial, podemos destacar a competência técnica desta unidade de ensino como sendo o conhecimento das principais metodologias ágeis de desenvolvimento e a habilidade em contrapô-las com a metodologia tradicional.

Sua atuação prática ainda orbitará a _XAX-Sooft_ e sua missão é implantar metodologia ágil nela _XAX-Sooft_, em quatro etapas:

1. levantar pontos frágeis da metodologia atual.
2. planejar a introdução de práticas do XP relacionadas aos princípios da comunicação e feedback.
3. planejar a introdução de práticas do XP relacionadas à integração contínua e testes.
4. adotar práticas contínuas de aprimoramento do modelo e de encantamento de novos clientes.

Nas próximas páginas será detalhada a primeira parte de nossa missão, proposta de conteúdo teórico sobre metodologias ágeis e novas abordagens da situação-problema. Bom trabalho!

# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/44cd329f-6b5f-4304-9486-64b31cb0d049/original)](https://ampli-images.s3.amazonaws.com/production/44cd329f-6b5f-4304-9486-64b31cb0d049/original)

### **Qual é o foco da aula?**

Nesta aula, você terá contato com fundamentos das metodologias ágeis, comparações com o modelo tradicional e a descrição de alguns princípios e práticas do XP, Scrum e FDD.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- examinar o processo tradicional de desenvolvimento;
- analisar o processo de desenvolvimento ágil;
- distinguir três processos de desenvolvimento ágeis: _Extreme Programming, Scrum e Feature-Driven Development._

**Situação-problema**

Os conteúdos apresentados na unidade 1 abordaram os fundamentos da Engenharia de _software_, passando pelo seu conceito, objetivos e princípios.Os processos de _software_ receberam o devido destaque e fundamentaram o estudo do ciclo de vida tradicional de desenvolvimento de um produto de _software_.

A exposição de todas as etapas desse ciclo deu a você a exata noção do modelo tradicional de criação de um sistema e te tornará apto a compará-lo com o que será estudado nesta unidade.

Por conta do sucesso do projeto de controle de clientes, a _XAX-Sooft_ assumiu outros compromissos com a empresa de games. Conforme a demanda cresce e a natureza das solicitações se concentra em torno de entregas mais rápidas, vai ficando mais clara a necessidade de adoção de procedimentos que acompanhem tais mudanças.

Embora a metodologia cascata tenha sido apropriada para determinada circunstância da vida da _XAX-Sooft_, seus dirigentes entendem que é chegado o momento de adotarem práticas que se apoiem em contatos regulares e produtivos com o cliente, em produção de programas executáveis em menor tempo e em estimativas mais realistas.

Desse cenário naturalmente despontam as metodologias ágeis. Elas diferem dos processos mais tradicionais em muitos aspectos, mas sobretudo naqueles que compõem as aspirações da _XAX-Sooft_.

Utilizando os temas que estão sendo abordados nesta aula e sua habilidade em diagnosticar procedimentos ativos, você deve criar um documento que contenha as fragilidades do processo atual, visando justamente justificar a mudança para um modelo ágil.

Esse documento também lhe servirá de base para providências futuras, incluindo a adoção das novas práticas. Eis o desafio!

Bom trabalho!

# **Processo tradicional de desenvolvimento**

[![](https://ampli-images.s3.amazonaws.com/production/f6839b4d-2a2c-4dfb-8035-eb7c22f7ce3e/original)](https://ampli-images.s3.amazonaws.com/production/f6839b4d-2a2c-4dfb-8035-eb7c22f7ce3e/original)

É possível que você conheça alguma organização que desenvolve _softwares_. Se conhece, é bastante provável que já tenha ouvido de algum membro dessa organização que o caminho entre o início do projeto e a entrega do produto esteja sendo trilhado com dificuldade crescente e que, embora exista processo formal de desenvolvimento, nem sempre os clientes estão satisfeitos com os resultados.

O processo tradicional de desenvolvimento baseia-se na construção linear do sistema, com sequência definida de fases, como mostra a figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/d8e68f0f-93f8-4205-8846-949a666e4c07/original)](https://ampli-images.s3.amazonaws.com/production/d8e68f0f-93f8-4205-8846-949a666e4c07/original)

Etapas do modelo tradicional de desenvolvimento. Fonte: adaptada de Teles (2004).

Além da linearidade, outras características – com raízes nas formas tradicionais de fabricação de bens de consumo – costumam estar presentes no desenvolvimento tradicional, cujo foco contempla o determinismo, especialização e foco na execução (TELES, 2004).

Para explicar esses conceitos cabe a analogia com o processo de montagem de veículos. Vejamos:

- materiais alimentam um processo de fabricação. Ao final, temos um automóvel terminado. As alterações pelas quais os materiais passam são **determinísticas** e devem sempre gerar um resultado conhecido. Acarreta segurança, redução de tempo e custo.
- a indústria tradicional divide o processo de montagem em inúmeras atividades especializadas, desenvolvidas por trabalhadores igualmente **especializados**.
- **foco na execução**: a fórmula é simples: determinismo + especialização = não há o que pensar. Basta executar.

Não é difícil de inferir que o modo tradicional tenha sido concebido com base nessas ideias de desenvolvimento industrial em linha. De acordo com elas, a mera obediência a eventos consecutivos (de requisitos até implantação), a especialização (funções de analista, projetista, programador, testador) e o foco na execução seriam capazes de criar um produto de qualidade, no tempo estipulado e sem ultrapassar o orçamento.

Havia, e ainda há, a presunção de que a sequência de etapas do projeto será transformada corretamente em _software_ (TELES, 2004).

_____

**➕ Pesquise mais**

Os benefícios da divisão de trabalho e da especialização para a produtividade do setor industrial são defendidos em um trecho do livro "A Riqueza das Nações", escrito em 1776 por Adam Smith. Para conhecê-lo melhor, leia o artigo “[_A fábrica de Alfinetes de Adam Smith_](https://economianostra.wordpress.com/2013/05/28/a-fabrica-de-alfinetes-de-adam-smith/)".

_____

Agora, considere a possibilidade de dividirmos nossos recursos humanos em dois tipos: trabalhadores manuais e trabalhadores do conhecimento.

O primeiro tipo desempenha trabalhos repetitivos, predeterminados e dependem principalmente das suas habilidades manuais e físicas para a execução de suas tarefas. Os trabalhadores do conhecimento, por sua vez, cumprem a missão com base em seu raciocínio, devem ter oportunidades de praticar sucessivas revisões em sua obra e não seguem processo linear em seus processos de criação.

Em qual dos dois tipos você classificaria um desenvolvedor de _software_? Acertou se pensou no trabalhador do conhecimento. No entanto, pela metodologia tradicional de desenvolvimento, são tratados como trabalhadores manuais.

O erro é tratado como “pecado” e o medo de errar torna os desenvolvedores defensivos. Há pouca possibilidade de reverem sua obra depois de pronta e seu trabalho se baseia num processo linear (TELES, 2004).

# **Processo ágil de desenvolvimento**

[![](https://ampli-images.s3.amazonaws.com/production/bc9e27f9-4e2c-417c-9d3a-745af7ebdcaf/original)](https://ampli-images.s3.amazonaws.com/production/bc9e27f9-4e2c-417c-9d3a-745af7ebdcaf/original)

Em sua essência, os métodos ágeis têm menos ênfase nas definições de atividades e mais ênfase nos fatores humanos do desenvolvimento (WAZLAWICK, 2013). São claramente mais adequados à natureza do trabalho de profissionais de TI, já que se baseiam na necessidade de sucessivas revisões na obra. Atividades intelectuais não são executadas de forma linear e não são determinísticas.

Durante a construção de um _software_, há que se considerar uma infinidade de detalhes que nem sempre são lembrados logo na primeira oportunidade.

Da mesma forma, ao tratar pela primeira vez das funcionalidades que deseja para o produto, o cliente ainda não as conhece por completo e não consegue ter visão global do que necessita. Que tal darmos a ele a oportunidade de aprender e mudar de ideia ao longo do processo de desenvolvimento?

______

🔁 **Assimile**

De acordo com o documento intitulado “Manifesto Ágil”, os métodos ágeis valorizam:

- indivíduos e interação entre eles mais que processos e ferramentas;
- _Software_ em funcionamento mais que documentação abrangente;
- colaboração com o cliente mais que negociação de contratos;
- responder a mudanças mais que seguir um plano (BECK, 2001).

______

Você certamente não se deparou com essa preocupação com o cliente quando estudou o modelo tradicional na unidade anterior.

> “O aprendizado do qual estamos tratando decorre do feedback que o software fornece ao cliente quando este o manipula. No desenvolvimento ágil, o conceito de feedback está presente ao longo de todo o desenvolvimento do software e exerce um papel fundamental.” (TELES, 2004, p. 42).

Como podemos proporcionar essa chance ao cliente? As práticas relacionadas aos métodos ágeis responderão. Veremos, em linhas gerais, três processos de desenvolvimento ágeis: _Extreme Programming, Scrum e Feature-Driven Development._

# **Visão geral do Extreme Programming (XP)**

[![](https://ampli-images.s3.amazonaws.com/production/68f1e564-e0ff-4fb4-8ffc-6d9afa9e56da/original)](https://ampli-images.s3.amazonaws.com/production/68f1e564-e0ff-4fb4-8ffc-6d9afa9e56da/original)

O XP é uma metodologia adequada para projetos que possuem requisitos que se alteram constantemente, para equipes pequenas e para o desenvolvimento de programas orientados a objetos.

É indicado também para ocasiões em que se deseja partes executáveis do programa logo no início do desenvolvimento e que ganhem novas funcionalidades assim que o projeto avança.

_____

**💭 Reflita**

O XP, assim como as outras metodologias ágeis, defende que a criação de um _software_ segue a mesma dinâmica da criação de uma obra de arte. O trecho que segue ilustra esse fato:

> “Escrever uma redação, um artigo ou um livro é uma atividade puramente intelectual que se caracteriza pela necessidade de sucessivas revisões e correções até que a obra adquira sua forma final. [...] Quando um pintor cria um novo quadro, é comum começar com alguns esboços, evoluir para uma representação mais próxima do formato final, fazer acertos, retoques e afins até que a obra esteja concluída.” (TELLES, 2004, p. 39).

_____

Você conhecerá agora como se compõe uma equipe de trabalho no XP e os valores do modelo.

**Equipe de trabalho**

Embora a especialização não seja estimulada nas metodologias ágeis, há necessidade de se estabelecer funções entre os participantes do projeto. Uma típica equipe de trabalho no XP tem a seguinte configuração (TELLES, 2004):

- gerente do projeto: responsável pelos assuntos administrativos, incluindo relacionamento com o cliente. Opera nos bastidores do projeto.
- _Coach_: responsável técnico pelo projeto. Deve ser tecnicamente bem preparado e experiente. Compete a ele assegurar o bom andamento do processo.
- analista de teste: ajuda o cliente a escrever os testes de aceitação e fornece feedback para a equipe interna de modo que as correções no sistema possam ser feitas.
- redator técnico: ajuda a equipe de desenvolvimento a documentar o sistema, permitindo que os desenvolvedores foquem a construção do programa propriamente dito.
- desenvolvedor: realiza análise, projeto e codificação do sistema. No XP, não há divisão entre estas especialidades.

**Valores do XP**

O Extreme Programming apoia-se em quatro pilares para atingir seus objetivos:

- _feedback_: quando o cliente aprende com o sistema que utiliza e reavalia suas necessidades, ele gera feedback para sua equipe de desenvolvimento.
- comunicação: entre equipe e cliente permite que os detalhes sejam tratados com atenção.
- simplicidade: implementar o que é suficiente para atender à necessidade do cliente.
- coragem: para melhorar o que já está funcionando.

# **Visão geral do Scrum**

[![](https://ampli-images.s3.amazonaws.com/production/c5d890a5-641d-479c-808c-1e709cb7e260/original)](https://ampli-images.s3.amazonaws.com/production/c5d890a5-641d-479c-808c-1e709cb7e260/original)

_Scrum_ é um modelo ágil para a gestão de projetos de _software_ que tem na reunião regular dos seus desenvolvedores para criação de funcionalidades específicas sua prática mais destacada.

Suas práticas guardam semelhança com as próprias do XP, mas possuem nomes e graus de importância diferentes nos dois contextos. Na sequência você terá contato com os principais elementos do _Scrum_.

**Principais elementos**

- _Product Backlog_: trata-se da lista que contém todas as funcionalidades desejadas para o produto. O _Scrum_ defende que tal lista não precisa ser completa logo na primeira vez em que é feita.

> “Pode-se iniciar com as funcionalidades mais evidentes [...] para depois, à medida que o projeto avançar, tratar novas funcionalidades que forem sendo descobertas.” (WAZLAWICK, 2013).

- _Sprint Backlog_: lista de tarefas que a equipe deverá executar naquele Sprint. Tais tarefas são selecionadas do _Product Backlog_, com base nas prioridades definidas pelo _Product Owner_.
- _Sprint_: o _Scrum_ divide o processo de efetiva construção do _software_ em ciclos regulares, que variam de duas a quatro semanas. Trata-se do momento em que a equipe se compromete a desenvolver as funcionalidades previamente definidas e colocadas no _Sprint Backlog_. Se alguma funcionalidade nova for descoberta, ela deverá ser tratada no Sprint seguinte. Cabe ao _Product Owner_ manter o _Sprint Backlog_ atualizado, apontando as tarefas já concluídas e aquelas ainda por serem concluídas.

**Membros da equipe**

Embora o modelo _Scrum_ defenda que as equipes sejam auto-organizadas, ainda assim apresenta três perfis profissionais de relevância:

- _Scrum Master_: trata-se de um facilitador do projeto, um agente com amplo conhecimento do modelo e que preza pela sua manutenção durante todas as etapas do projeto. Deve atuar como moderador ao evitar que a equipe assuma tarefas além da sua capacidade de executá-las.
- _Product Owner_: é a pessoa responsável pelo projeto propriamente dito. Ele tem a missão de indicar os requisitos mais importantes a serem tratados nos Sprints.
- _Scrum Team_: é a equipe de desenvolvimento, composta normalmente por seis a dez pessoas. A exemplo do Extreme Programming, não há divisão entre programador, analista e projetista (WAZLAWICK, 2013).

_____

**📝 Exemplificando**

A Vodafone é uma das maiores empresas de telecomunicações do mundo. Sua divisão da Turquia, fundada em 2006, era, no ano de 2014, a segunda maior empresa do ramo naquele país. Por meio de processo baseado em três passos básicos, a corporação tem buscado encantar seus clientes por meio do que chamam “transformação ágil”. No primeiro passo, uma equipe piloto de desenvolvimento foi estabelecida e, em um número determinado de Sprints, seu progresso foi medido e registrado.

Devido às melhorias observadas na produtividade da equipe piloto – que havia triplicado seu desempenho ao final dos primeiros três meses – ficou definido que o passo dois seria iniciado, com a criação de novas equipes de _Scrum_.

Cerca de cinco meses após o aumento das equipes em quantidade, observou-se que o desempenho havia aumentado duas vezes. Além disso, foram observadas reduções significativas nas reclamações dos clientes em relação a essas equipes.

Esse sucesso levou a organização a criar uma unidade ágil autônoma, chamada “_Agile Solutions_”, que atualmente funciona com seis equipes _Scrum_. Novas equipes, com novas responsabilidades, logo serão criadas.

O próximo passo é crescer e fortalecer a “_Agile Solutions_” e, em seguida, avançar para o terceiro passo, que é a adoção da metodologia em toda a organização, a fim de fazer crescer a cultura ágil na Vodafone.

# **Visão geral do Feature-Driven Development (FDD)**

[![](https://ampli-images.s3.amazonaws.com/production/531c6948-6a27-4dce-9fec-994ee19a7993/original)](https://ampli-images.s3.amazonaws.com/production/531c6948-6a27-4dce-9fec-994ee19a7993/original)

O FDD ou _Feature-Driven Development_ (Desenvolvimento Dirigido por Funcionalidade) é um método ágil que enfatiza o uso de orientação a objetos e possui apenas duas grandes fases:

a) concepção e planejamento: o modelo sugere que se conceba e planeje o produto por uma ou duas semanas antes de começar a construir.

b) construção: desenvolvimento por iterações do produto em ciclos de uma a duas semanas.

A primeira fase inclui três subfases:

- **DMA (**_**Desenvolver Modelo Abrangente**_**)**: etapa na qual especialistas estabelecidos em grupos desenvolvem um modelo de negócio amplo, representado por diagramas.
- **CLF (Construir Lista de Funcionalidades)**: atividade inicial que abrange todo o projeto, com o objetivo de identificar todas as funcionalidades que satisfaçam os requisitos levantados.
- **PPF (Planejar por Funcionalidade)**: nesta etapa é definida a ordem em que as funcionalidades serão implementadas, com base na disponibilidade da equipe de desenvolvimento, na complexidade e nas dependências entre as funcionalidades.

A fase de construção inclui outras duas subfases:

- **DPF (Detalhar por Funcionalidade)**: momento em que o design de implementação da funcionalidade é criado, por meio de diagramas de sequência ou comunicação.
- **CPF (Construir por Funcionalidade)**: fase em que se produz efetivamente código para as funcionalidades escolhidas (WAZLAWICK, 2013).

_____

**💪 Faça você mesmo**

A fim de colocá-lo em contato com situações em que a mudança para o modelo ágil foi encarada como solução para pontos frágeis do processo de desenvolvimento, pesquise outros casos de sucesso na adoção do modelo ágil. A internet está repleta deles.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

Alguns clientes importantes da _XAX-Sooft_, incluindo o vendedor de games, têm demonstrado certa insatisfação com o fato de não verem, logo em etapas iniciais dos projetos, seus investimentos revertidos em funcionalidades que possam ser usadas e experimentadas. Argumentam que, caso pudessem ter testado certas partes do programa antes de atingirem seus respectivos formatos finais, não teriam demandado tantas mudanças nas fases finais do projeto e, por consequência, despendido mais recursos.

Se a _XAX-Sooft_ tem seguido com rigor e competência os procedimentos definidos, por qual motivo tantas alterações são solicitadas pelos clientes? Que indicação de solução você daria ao caso?

Na situação-problema foi proposto o desafio de relatar os pontos de atenção e as fragilidades da metodologia assumida, a fim de justificar a intenção de mudança futura de modelo.

Idealmente, este relatório deverá pontuar que:

1. o modelo tradicional, por sua própria natureza, não apresenta pontos de _feedback_ regulares com o cliente, de modo a deixá-lo a par do que está sendo desenvolvido e oportunizar a utilização de algumas funcionalidades já em condições de serem executadas.
2. em função desta característica, o modelo atual não oferece ao cliente momentos em que ele possa aprender com o que já está pronto e mudar o rumo – se for o caso – das próximas funcionalidades. Em outras palavras, o cliente tem pouca chance de mudar de ideia.
3. por conta da estrutura linear do modelo tradicional, as etapas do processo devem ser integralmente concluídas antes de serem sucedidas pela próxima, o que implica falta de oportunidades para rever o trabalho feito naquela fase e na propagação de uma falha em etapas mais adiantadas do projeto.
4. a implementação das funcionalidades do sistema nunca é feita pelo mesmo profissional que levantou os requisitos e desenhou a solução, já que todas as funções são especializadas. Há pouca comunicação entre os membros da equipe e não raro algumas tarefas são repetidas ou sequer cumpridas.

_____

**⚠️ Atenção**

A mudança de um modelo para outro não é uma atividade simples e imediata. Ao contrário, implica mudanças culturais, de atitude e de desapego ao que estava funcionando na metodologia antiga. É comum que alguns interesses sejam contrariados durante o processo.

______

**📌Lembre-se**

O cliente deixou de ser figura indesejada durante o processo de desenvolvimento para se tornar peça importante na validação das funcionalidades e na correção pontual de falhas derivadas da má qualidade da comunicação entre ele e a equipe.