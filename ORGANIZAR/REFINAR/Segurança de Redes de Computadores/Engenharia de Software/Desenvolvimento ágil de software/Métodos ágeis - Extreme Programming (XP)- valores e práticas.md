# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/e0909382-0266-411e-bae6-0c452388fe87/original)](https://ampli-images.s3.amazonaws.com/production/e0909382-0266-411e-bae6-0c452388fe87/original)

### **Qual é o foco da aula?**

Nesta aula, nosso foco está em apresentar o Extreme Programming. Este modelo fundamenta-se em quatro valores que inspiram suas práticas.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- examinar as práticas que se relacionam mais diretamente com comunicação;
- identificar como surgiu o modelo de programação em pares;
- analisar o modelo de código de propriedade coletiva da equipe.

**Situação-problema**

Como se espera de toda organização atenta aos avanços das práticas de desenvolvimento, a _XAX-Sooft_ novamente está prestes a promover mudanças em sua forma de gerir projetos de _software_. Das experiências passadas deverão permanecer apenas as que contribuíram para tornar a empresa sólida e bem percebida pelo mercado em que atua.

As práticas que remetiam a processos antigos darão lugar a procedimentos ágeis, objetivos, bem focados e em consonância com um novo perfil de cliente e de profissional de TI. A melhor notícia é que você, estudante, será o responsável direto por essa mudança.

Concluído o levantamento dos pontos ineficientes do modelo atualmente praticado, sua missão agora é promover a gradual, dirigida e irreversível passagem para o modo ágil de se desenvolver produtos de _software_. Com isso, mais habilidades são desenvolvidas para atender a competência geral que é: conhecer as principais metodologias de desenvolvimento de _software_, normas de qualidade e processos de teste de _software_.

Ao estudar os métodos ágeis podemos conhecer tecnicamente as principais metodologias ágeis de desenvolvimento e a habilidade em contrapô-las com a metodologia tradicional.

O processo de mudança de modelo deverá ser dividido em duas etapas. Cada uma marcada pela implantação de práticas que estejam relacionadas, respectivamente, com comunicação e _feedback_.

Para que você se saia bem nesse desafio, é preciso que se empenhe na compreensão dos pontos desenvolvidos na aula. sua missão será facilitada se for capaz de entender a real intenção dos criadores do modelo quando propuseram que o cliente fosse figura presente durante todo o desenvolvimento.

Em resumo, nessa etapa do desafio você deverá criar documentação que contenha o planejamento da implantação das práticas de: cliente presente, jogo do planejamento, programação em par, código coletivo, _stand up meeting_ e metáforas.

Eis o desafio. Bom trabalho!

# **Cliente presente**

[![](https://ampli-images.s3.amazonaws.com/production/102ec5b2-49b1-42e7-b6e7-bbfad19cced6/original)](https://ampli-images.s3.amazonaws.com/production/102ec5b2-49b1-42e7-b6e7-bbfad19cced6/original)

Esta primeira prática assume o papel principal no processo de quebra de paradigmas proposto pelo XP. Afinal, quando adotamos o modelo tradicional, nunca consideramos como válida – sequer aconselhável – a presença efetiva do cliente durante o desenvolvimento de um programa. Via de regra, a participação dele no projeto se dava apenas no momento da coleta de requisitos e na implantação do sistema.

O modelo ágil, no entanto, sugere que o cliente deve conduzir o desenvolvimento a partir da utilização do sistema e sua proximidade da equipe viabiliza esta condução. Essa prática nos revela que para Teles (2004):

[![](https://ampli-images.s3.amazonaws.com/production/201582d0-0220-493e-a005-07e75d0770df/original)](https://ampli-images.s3.amazonaws.com/production/201582d0-0220-493e-a005-07e75d0770df/original)

A viabilização da presença do cliente no projeto se dá, entre outros meios, pelo estabelecimento do que se chama sala de guerra, ou _War Room_. Nela deve ser colocada uma mesa na qual o cliente poderá desenvolver suas tarefas, próximo da equipe e durante o andamento do projeto. Enquanto trabalha, o cliente poderá ser consultado e, ao escutar informação incorreta, poderá corrigi-la no ato.

______

**🔁 Assimile**

O XP incentiva que a comunicação seja feita, de preferência, presencialmente. Este trecho sintetiza os motivos.

> “É importante notar que, em uma comunicação face a face, existe uma riqueza de elementos que facilitam a compreensão da nossa mensagem,além de uma dinâmica que viabiliza questionamentos e respostas." (TELES, 2004, p. 47).

# **O jogo do planejamento**

[![](https://ampli-images.s3.amazonaws.com/production/ad12b048-c7af-4578-8bfd-afadd338f457/original)](https://ampli-images.s3.amazonaws.com/production/ad12b048-c7af-4578-8bfd-afadd338f457/original)

Que tal se, ao invés de você escutar do cliente o que ele tem a dizer sobre as funcionalidades e fazer suas anotações, a síntese das funções fosse feita por ele, de próprio punho? Pois é assim que o XP orienta que se inicie o planejamento do sistema.

Ao cliente é dado um cartão, com aproximadamente metade de uma folha tamanho A4, na qual ele deverá escrever uma (e apenas uma por cartão) funcionalidade que deseja para o programa, de forma simples e objetiva.

Você pode achar essa prática um tanto diferente, mas vale a reflexão: será que o cliente não passará a dar mais valor àquilo que ele próprio está escrevendo? Não haverá, portanto, maior responsabilidade dele em relação ao que está pedindo? Sem contar que, ao registrar ele próprio um requisito, a possibilidade de mal-entendido em relação a ele cai consideravelmente.

Cada ficha leva o nome de história. Elas são a base para o planejamento dos desenvolvedores, que podem dividir a história em tarefas, em nome de um planejamento mais preciso e caso as histórias sejam extensas demais para apenas um dia de trabalho.

_____

**📝 Exemplificando**

Podem ser considerados bons exemplos de histórias:

- apresente ao cliente as dez tarifas mais baratas para uma determinada rota;
- para cada conta, computar o saldo fazendo a adição de todos os depósitos e a subtração de todas as deduções;
- a tela de login deve permitir que o usuário pule o login. Neste caso, o usuário entrará no sistema como convidado;
- o usuário deve poder alterar seu perfil. Dois campos de senha para confirmação.

_____

É comum que, ao considerarmos a duração de uma tarefa, a estimativa seja feita em horas. O XP, no entanto, adota como unidade o dia ideal, que representa um dia no qual o desenvolvedor trabalha apenas nas implementações das funcionalidades, sem telefone, reuniões ou outras interrupções ou imprevistos.

A pergunta que se faz é: “Se eu tiver o dia todo para implementar determinada história, quantos dias levarei para finalizá-la?” Cada dia ideal representa, para a equipe, um ponto, que é a unidade de medida usada para estimar e acompanhar todas as histórias (TELES, 2004).

Para fins de controle, os pontos estimados para aquela história são registrados no canto superior esquerdo do cartão e os pontos já consumidos são registrados no canto superior direito do cartão.

É normal que neste ponto você esteja questionando a perfeita viabilidade de se estimar o desenvolvimento desta forma. Contudo, alguns procedimentos podem ser adotados pela equipe para tornar esse método bem interessante:

- resgatar cartões que já tenham sido implementados e que sejam semelhantes ao que está sendo estimado pode oferecer boa noção sobre investimento de tempo na história;
- a equipe deve se aproveitar do registro dos pontos efetivamente consumidos para estimar. A experiência com funcionalidades semelhantes também vale;
- a prática recomenda que estimativas sejam feitas em conjunto, como forma de unir experiências e sentimentos e mitigar a possibilidade de erros. E sim, o cliente deve estar presente nas estimativas, tornando menor a chance de premissas incorretas.

Como uma das bases do modelo ágil é a oferta regular de artefato executável ao cliente, a equipe deve planejar muito bem as entregas das funcionalidades, ou os _**releases**_.

_____

**📝 Exemplificando**

Um bom exemplo de como os releases podem ser distribuídos é o que segue. São quatro releases com oito semanas de intervalo entre cada um, para um site de vendas on-line:

R1: consulta dos produtos em estoque

R2: processamento das compras on-line

R3: acompanhamento dos pedidos

R4: campanha de marketing de relacionamento

_____

Os _releases_ devem ser oferecidos em intervalos curtos, tipicamente de 2 meses (TELES, 2004).

Confirmando a participação efetiva do cliente no projeto, o XP prevê que ele (cliente) deve estabelecer a ordem dos releases com base em suas necessidades. Devem ser levadas também em conta as dependências técnicas, naturalmente.

Durante o desenvolvimento do primeiro release, o cliente usará o sistema várias vezes, o que o ajudará a escolher as histórias das próximas entregas. Durante um release, um cliente poderá alterar as histórias se considerar necessário, fazendo uso do seu aprendizado no sistema, já que o XP não visa blindar a equipe de desenvolvimento das mudanças.

Em processos tradicionais, o escopo é fechado no início do projeto. No XP, o escopo deve se alterar ao longo do projeto.

# **Programação em par**

[![](https://ampli-images.s3.amazonaws.com/production/a97fdaca-5290-4ee0-ae2e-4f1c32cb58fd/original)](https://ampli-images.s3.amazonaws.com/production/a97fdaca-5290-4ee0-ae2e-4f1c32cb58fd/original)

Desenvolvedores não trabalham sozinhos num projeto XP. Você também pode achar pouco convencional, mas na programação em par, dois programadores trabalham em um mesmo problema, ao mesmo tempo. Aliás, quem foi que disse que o XP é convencional? Veja adiante.

Em determinado momento, o condutor assume o teclado e o navegador acompanha o trabalho, fazendo revisões e sugestões. Em outro, há revezamento de papéis. As correções são feitas no momento da programação, evitando que pequenos erros se tornem grandes problemas no futuro.

A condução da programação deve ser realizada, em tempos alternados, pelos dois programadores. Eles devem se alternar, escrevendo código a cada 15 ou 20 minutos. O programador que não estiver escrevendo verifica cuidadosamente o código, enquanto ele está sendo criado pelo seu companheiro (SCHACH, 2008).

A prática influencia na boa modelagem da solução, que passa a ser fruto do entendimento e da conversa entre os pares. Se um parceiro concebe algo muito complexo, o outro pode propor solução mais simples (TELES, 2004).

O par exerce pressão positiva no desenvolvimento, evitando distrações de e-mail,bate-papos, cansaço, desânimo momentâneo. O compromisso deixa de ser individual e passa a ser também em relação ao par.

Além de reduzir as chances de defeitos na programação, essa prática tende a tornar o conhecimento geral da equipe mais homogêneo e contribuir para o aprendizado contínuo.

Você pode estar quase convencido de que a programação em par é a solução para todos os problemas da criação de um código. Infelizmente esta não é a realidade.

Para boa parte dos gerentes, desenvolvedores são vistos como máquinas e o projeto como uma fábrica e, de acordo com a lógica industrial, deve-se obter mais produção de uma mesma “máquina”. Acontece que já estamos alertados: o que se aplica para a produção em massa não se aplica ao desenvolvimento de _software_, não é mesmo?

_____

**💭 Reflita**

A programação em par é, de fato, imune a contratempos? Reflita.

Na prática, foram observados alguns inconvenientes na programação em duplas. Por exemplo, ela requer grandes blocos ininterruptos de tempo, e os profissionais poderão ter dificuldades em alocar períodos de tempo de 3 a 4 horas ininterruptas. Além disso, nem sempre funciona bem com indivíduos tímidos ou autoritários, ou com dois programadores inexperientes (SCHACH, 2008, p. 57).

# **Código coletivo e Stand up meeting**

[![](https://ampli-images.s3.amazonaws.com/production/4a7e3cb0-e21a-48dc-8e12-4bc531d9e520/original)](https://ampli-images.s3.amazonaws.com/production/4a7e3cb0-e21a-48dc-8e12-4bc531d9e520/original)

Já que o XP sugere a programação em par e, neste contexto, o rodízio de programadores, é normal que toda a equipe seja responsável pelo código que está sendo produzido. Sendo assim, não será necessária autorização para que seja alterado arquivo, por quem quer que seja, desde que mantido o padrão estabelecido.

Você entende melhor agora o porquê de a coragem ser um dos valores do XP? Estimar histórias na presença do cliente, deixando-o priorizar as funcionalidades e manter o sistema simples são mais indicativos de que o uso do XP requer coragem.

A prática do código coletivo pode ter o efeito benéfico de evitar “ilhas de conhecimento”, ou seja, profissionais que detenham conhecimento quase exclusivo sobre determinado projeto.

O “sabe tudo” pode se ausentar por doença, férias, viagem ou mesmo deixar a empresa repentinamente e os demais colaboradores poderão não saber alterar partes do projeto cujo conhecimento é quase exclusivo da “ilha”.

Outro efeito importante do código coletivo é que, quando todos o acessam, o código tende a ser mais bem revisado.

Uma das práticas mais simples e de implementação mais imediata é a _**stand up meeting**_ (reunião feita em pé). Um dia de trabalho no XP começa com uma reunião rápida, com não mais do que 10 minutos de duração e que serve para que todos os membros da equipe comentem o trabalho do dia anterior e planeje o dia atual.

Ao final da stand up, cada membro saberá o que deve fazer ao longo do dia. Esta prática pode gerar bons resultados, já que cada membro da equipe terá a visão geral do andamento do trabalho (TELES, 2004).

Em tempo: aconselha-se que a reunião seja feita todos os dias e com todos os participantes em pé, de modo a evitar prolongamento excessivo do tempo da conversa.

# **Metáforas**

[![](https://ampli-images.s3.amazonaws.com/production/480caaad-f29a-4899-b53d-5a0e6be73df8/original)](https://ampli-images.s3.amazonaws.com/production/480caaad-f29a-4899-b53d-5a0e6be73df8/original)

Visando promover a boa comunicação entre a equipe, sugere-se a adoção do uso de metáforas em pontos-chave do projeto, como na definição de um nome que seja comum à equipe e simbolize algo de fácil assimilação, como, por exemplo:

"Vamos chamar nosso projeto de ‘cartão de ponto’, para um sistema que gerencie as batidas de ponto de funcionários, gerando o provisionamento financeiro e mensal para módulo de folha de pagamento". Leia mais em “[_Extreme Programming – Conceitos e Prátic_](https://www.devmedia.com.br/extreme-programming-conceitos-e-praticas/1498#ixzz3sViVUxVT)[a](https://www.devmedia.com.br/extreme-programming-conceitos-e-praticas/1498#ixzz3sViVUxVT)”.

A metáfora deve ser utilizada, inclusive, para facilitar o entendimento do modelo XP (ou de uma funcionalidade do sistema) por parte do cliente. Imagine uma equipe de voleibol. Há jogadores mais especializados na defesa, outros no ataque e um que deverá fazer o último passe para o atacante buscar o ponto. No entanto, por conta do rodízio obrigatório de posições, em algum momento um atacante se verá na necessidade de defender uma bola, um levantador de atacar e assim por diante. Alguma similaridade com o XP?

_____

**➕ Pesquise mais**

Podemos encontrar boa definição formal da figura de linguagem metáfora em na matéria _“_[_Metáfora - Figura de palavra, variações e exemplos_](https://educacao.uol.com.br/disciplinas/portugues/metafora-figura-de-palavra-variacoes-e-exemplos.htm)_”_

_____

**💪 Faça você mesmo**

Uma das bases do pensamento do XP é a de que mais vale um programa rodando do que sua perfeita documentação. Contudo, isso não significa que a documentação deva ser negligenciada ou ignorada. Sua tarefa é fazer levantamento de ao menos 4 documentos que devem ser gerados durante um projeto conduzido pela metodologia XP.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/68113b61-e3c2-407d-afcd-97e007f0e88a/original)](https://ampli-images.s3.amazonaws.com/production/68113b61-e3c2-407d-afcd-97e007f0e88a/original)

É do senso comum entre profissionais de TI que a metodologia XP, para atingir sua plenitude e ser efetiva, deve ser implantada em sua totalidade. Sua adoção parcial, embora possa trazer algum benefício momentâneo, não deverá ser entendida como regra. Há, contudo, a sensação de que a implantação das práticas deva ser gradual.

A troca repentina e integral de uma metodologia em uma organização que sempre a praticou poderá ser, no mínimo, traumática. É justamente a mudança gradual e controlada que nosso desafio propõe.

Apenas para resgatarmos o que foi descrito na situação-problema, na primeira etapa de mudança para o modelo ágil, deverão ser implantadas as práticas mais proximamente relacionadas à comunicação e ao _feedback_, quais sejam cliente presente, jogo do planejamento, programação em par, código coletivo, _stand up meeting_ e metáforas. Uma abordagem possível para tal inflexão é a que segue:

1. já que o principal objetivo a ser atingido nesta primeira etapa é a melhoria em todos os meios de comunicação, nada mais imediato do que chamar o cliente ao projeto. Haverá, por certo, resistência em participar tão ativamente do projeto num primeiro momento, mas nada como usar o apelo das entregas regulares e feitas em períodos pequenos para convencê-lo de que, quanto mais próximo ele estiver da equipe, mais corretamente implementadas estarão as funcionalidades.
2. para a efetivação da nova maneira de coletar e tratar os requisitos – aqui chamada de Jogo do Planejamento – a inclusão do cliente no processo já deverá ter sido consolidada. De novo, é possível que haja resistência em escrever – ele próprio – o que deseja para o projeto.
3. por demandar providências meramente organizacionais e internas, a programação em par é uma das práticas de mais fácil adoção no contexto. Você deve acompanhar, no entanto, o desempenho dos programadores ao atuarem em duplas, já que esta nova configuração de trabalho pode vir acompanhada de pequenos conflitos entre os colegas, perda de foco, autoritarismo de um dos elementos em relação ao outro, entre outras ocorrências.
4. o código coletivo, a stand up meeting e o uso de metáforas também inspiram relativa facilidade em suas implementações. Vale promover a conscientização da equipe em relação a mudanças inoportunas no código e a eventual fuga do padrão de codificação estabelecido. Embora todos possam ter acesso irrestrito aos arquivos, é necessário o registro das alterações feitas.

Em relação às reuniões diárias, na condição de gestor você deve acompanhar os primeiros encontros e atuar como moderador da equipe, cuidando para que a duração da reunião não ultrapasse o estabelecido e que os assuntos devidos sejam tratados.

_____

**⚠️ Atenção**

O que costuma ser mais trabalhoso na venda do XP é mostrar suas vantagens para a área de TI da empresa cliente. A maioria dos profissionais da área teve formação acadêmica voltada para o desenvolvimento tradicional, o que os acostumou a outro conjunto de premissas e pouco propensos a abandoná-las facilmente (TELES, 2004).

_____

**📌Lembre-se**

A implantação de prática do XP, em conjunto ou de forma isolada, deve ser norteada pelo bom senso. O gestor não deve colocar rotinas novas para a equipe sem antes motivar seus membros para sua completa adoção.