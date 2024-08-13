# **Introdução da unidade**

[![](https://ampli-images.s3.amazonaws.com/production/e00633e0-a806-45c0-93ed-4371c3ace45d/original)](https://ampli-images.s3.amazonaws.com/production/e00633e0-a806-45c0-93ed-4371c3ace45d/original)

### **Objetivos da Unidade**

Ao longo desta Unidade, você irá:

- identificar os fundamentos de qualidade e da gestão da qualidade do _software_;
- examinar os fatores que afetam a qualidade e as ações de Garantia da Qualidade do _Software_ (SQA);
- esclarecer as normas de qualidade mais referenciadas;
- apontar métricas e inspeções de _software_.

### **Introdução da Unidade**

Olá, estudante! Iniciamos à terceira unidade da disciplina de Engenharia de _software_. Nas duas primeiras unidades deste material você teve a oportunidade de conhecer dois modos distintos, quase antagônicos, de desenvolvimento de _software_: o modelo tradicional e o modelo ágil.

Antes deles, no entanto, você foi conduzido até os fundamentos da engenharia de _software_ e à teoria associada ao processo de desenvolvimento de um produto; bases necessárias para sua entrada no universo das metodologias de desenvolvimento que seriam abordadas na sequência.

Conforme o conteúdo teórico era apresentado, a história da _XAX-Sooft_ era contada. No início, tínhamos uma empresa pequena e sem metodologia formal implantada. Com a chegada de um grande cliente, surgiu também a necessidade de organização dos seus processos e da adoção de um modelo de desenvolvimento para seu produto. A metodologia Cascata foi introduzida e, passado algum tempo, o _Extreme Programming_ passou a ser o modelo oficial de desenvolvimento.

É fato que a _XAX-Sooft_ evoluiu. No entanto, o modelo utilizado, por melhor e mais moderno que seja, não dispensa uma providência elementar: o gerenciamento da qualidade do produto. O objetivo geral desta unidade é que você se torne capaz de gerenciar por completo a qualidade do produto e do processo utilizado para criá-lo.

Você deverá desenvolver competência técnica para conhecer e conduzir processos de qualidade de _software_. Assim, atingirá os objetivos e desenvolverá as competências desta unidade por meio da resolução da realidade profissional em quatro etapas, criando relatórios contendo o levantamento de:

- práticas de qualidade atualmente implementadas;
- fatores que afetam a qualidade dos produtos;
- processo de implantação de norma de qualidade na _XAX-Sooft;_
- processo de implantação de inspeções, medições e métricas de _software_.

A seguir será detalhada a primeira parte de nossa missão, o conteúdo teórico proposto sobre qualidade de _software_ e novas abordagens da situação-problema.

Bom trabalho!

# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/8cf06b30-ab7c-4693-8f16-6489536dc2e3/original)](https://ampli-images.s3.amazonaws.com/production/8cf06b30-ab7c-4693-8f16-6489536dc2e3/original)

### **Qual é o foco da aula?**

Nesta aula, você terá contato com o conceito de qualidade e com sua gestão no processo de desenvolvimento de um _software_.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- esclarecer a importância da qualidade para o sucesso de um produto;
- examinar o conceito de qualidade;
- identificar os fatores de qualidade.

**Situação-problema**

O conteúdo teórico apresentado na unidade 2 abordou três das principais metodologias ágeis usadas para desenvolvimento de _software_ e ajudou você a trilhar o caminho até a efetiva implantação do _Extreme Programming_ na _XAX-Sooft_.

O modo ágil de se conduzir um projeto já foi incorporado ao cotidiano da equipe e as entregas seguem sendo feitas, na grande maioria das vezes, no prazo e no limite do orçamento combinados. O encantamento do cliente, de certa forma a grande meta a ser alcançada pela direção da empresa, tem sido verificado por meio de bons retornos dados à equipe por quem a contratou.

O aprimoramento da qualidade do processo e do produto deve ser, no entanto, desafio constante na vida da _XAX-Sooft_ e de qualquer outra empresa. Por esse motivo – e por alguns outros que lhe serão apresentados no decorrer desta unidade – ações específicas de garantia da qualidade do produto devem ser tomadas. Afinal, a obtenção de produto de qualidade é uma das justificativas da existência da própria Engenharia de _Software_ como disciplina estruturada.

Para que seu aproveitamento nesta aula e nas seguintes seja ótimo, há questões importantes a serem respondidas: afinal, o que é qualidade? Estamos tratando de uma percepção subjetiva ou de um conceito puramente objetivo? Um bom produto criado há 30 anos seria hoje considerado um produto de qualidade? Intrigante, não acha?

Utilizando os temas que estão sendo abordados nesta aula e sua crescente habilidade em diagnosticar situações e procedimentos ativos na empresa, você deve criar um relatório contendo o levantamento das práticas de qualidade atualmente implementadas.

Nesse relatório devem ser descritas as ações atualmente tomadas para que o produto da _XAX-Sooft_ esteja adequado ao seu propósito e em conformidade com os requisitos.

Na aula você terá contato com fundamentos de qualidade de _software_ e sua gestão. Um excelente aproveitamento dos seus estudos é o que desejamos a você.

# **Conceito de qualidade**

[![](https://ampli-images.s3.amazonaws.com/production/9f0e50b0-153b-43fb-8b67-c428dabd42ed/original)](https://ampli-images.s3.amazonaws.com/production/9f0e50b0-153b-43fb-8b67-c428dabd42ed/original)

Não se pode conceber um produto, qualquer que seja sua natureza, que não seja criado levando-se em conta sua qualidade. A busca por níveis satisfatórios e previamente definidos de excelência deve basear qualquer processo de fabricação em larga escala ou de manufatura, sob pena de se obter produto com baixa aceitação de mercado.

O que é qualidade de _software_ e por que ela é tão importante? Uma boa maneira de começarmos esta discussão é afastando a ideia de que qualidade signifique perfeição. É comum entendermos que sempre será possível encontrar algo a ser melhorado em algo que se reconhece como de boa qualidade.

Também não se pode caracterizar a qualidade como algo absoluto, definitivo e que tenha meios de ser medida universalmente, em parâmetros aceitáveis para todas as pessoas. O que parece ser de boa qualidade para mim pode não parecer para você. E vice-versa.

Por ser considerada um conceito de muitas dimensões, talvez uma boa maneira de começarmos a entender a qualidade, é que esta se realiza por meio de um conjunto de características e atributos de um certo produto. Como qualidade não significa perfeição, é natural que tenhamos que estabelecer um nível aceitável de qualidade para um produto e meios para verificar se esse nível foi alcançado.

Embora saibamos que traços de subjetividade e a perspectiva própria do avaliador farão parte de uma avaliação, o “nível aceitável” de qualidade precisa ser o mais objetivo possível, extraído por meio de processos estruturados e ferramentas apropriadas de medição de qualidade.

Ao longo dos anos, autores e organizações têm definido o termo qualidade de formas diferentes. Para Crosby (1979, p. 23), qualidade é a:

> "conformidade com os requisitos do usuário".

Para ele, se o produto atende aos requisitos explícitos e implícitos, significa que o produto é de qualidade.

Por exemplo, ao comprarmos uma televisão, se os nossos requisitos estiverem de acordo com as suas características, o aparelho então nos serve. Caso contrário, escolhemos alguma outra que esteja mais próxima de nossas expectativas.

Humphrey (1989, p. 280) refere-se à qualidade como:

> "a conquista de excelentes níveis de adequação ao propósito".

Enquanto a IBM cunhou a frase "qualidade dirigida ao mercado", que se baseia na conquista total da satisfação do cliente.

A expressão "adequação ao propósito" pressupõe a existência de um registro da descrição do propósito do produto. Tomando-se como exemplo um secador de cabelos, seu próprio nome carrega sua funcionalidade. Características técnicas são colocadas num manual de instruções. No caso de um _software_, seu propósito está inserido na especificação de requisitos.

Mais recentemente, a qualidade foi definida pela norma ISO 9001- 00 como:

> "o grau no qual um conjunto de características inerentes preenche os requisitos".

______

**🔁 Assimile**

Observe outros dois conceitos e ideias relacionados à qualidade:

> “Qualidade de Software é um processo sistemático que focaliza todas as etapas e artefatos produzidos com o objetivo de garantir a conformidade de processos e produtos, prevenindo e eliminando defeitos.” (BARTIÉ, 2002, p. 16)
> 
> "Qualidade é a totalidade das características de um produto de _software_ que lhe confere a capacidade de satisfazer necessidades implícitas e explícitas.” (ISO/IEC 9126-1, 2003, p. 17).

# **Fatores de qualidade**

[![](https://ampli-images.s3.amazonaws.com/production/4ca1919d-efd0-4408-acd6-2b55e1d99fc6/original)](https://ampli-images.s3.amazonaws.com/production/4ca1919d-efd0-4408-acd6-2b55e1d99fc6/original)

Você já deve ter se perguntado: o que define, afinal, um bom _software_? É de se esperar que nesta resposta apareçam os elementos que compõem o conceito de qualidade dos quais tratamos há pouco.

Uma das possíveis medidas de qualidade é, de fato, a adequação ao propósito, o que significa que o _software_ funciona efetivamente de acordo com o que foi projetado.

Shaffer (2013) propõe uma forma interessante de se medir a qualidade de um _software_ que é o seu valor de mercado, especialmente em situações em que alguém está procurando investir na empresa que o produz. É muito comum também que as pessoas percebam a qualidade de um _software_ como reflexo da qualidade do processo usado para criá-lo.

Embora você possa não encontrar uma definição universal e definitiva para a qualidade aplicada a um _software_, fatores como a corretude, a eficiência e a usabilidade são algumas medidas amplamente aceitas como indicadores da qualidade do produto.

Esses fatores serão estudados com mais propriedade e detalhes na próxima aula, mas vale uma olhada agora:

- **corretude**: capacidade do _software_ em executar suas funcionalidades conforme elas foram definidas. Se pudéssemos resumir esse fator em uma pergunta, ela seria próxima de: “o _software_ faz aquilo que eu quero?”
- **eficiência**: relaciona-se ao grau de adequação do programa aos recursos de hardware, tais como processador e memória. Eficiência é uma palavra muito comumente usada, embora muitas vezes de forma incorreta. Para ele, eficiência é a medida de quantos recursos são usados para que uma tarefa seja completada. Atualmente, com o hardware custando tão pouco, não se presta muita atenção no fator eficiência como no passado, exceto em processos que incluem quantidade muito grande de dados, como o Big Data, por exemplo (SHAFFER, 2013).
- **usabilidade**: este fator está relacionado com a facilidade de uso do produto. Em outras palavras, trata-se da medida da capacidade do público-alvo em obter valor do _software_ por meio da sua interface.
- **portabilidade**: é possível usá-lo em outra plataforma? Trata-se da medida de facilidade em mudar o _software_ de uma plataforma (Windows, por exemplo) para outra (Mac, por exemplo).
- **interoperabilidade**: trata-se da “capacidade de diversos sistemas e organizações trabalharem em conjunto (interoperar) de modo a garantir que pessoas, organizações e sistemas computacionais interajam para trocar informações de maneira eficaz e eficiente”.

_____

**➕ Pesquise mais**

Para saber mais sobre o tema, leia o artigo “[Padrões de Interoperabilidade](https://www.gov.br/governodigital/pt-br/governanca-de-dados/padroes-de-interoperabilidade)”, nele você encontrará explicações acerca de interoperabilidade, padrões de interoperabilidade (ePING) e integração.

_____

Com essas características, você começa a entender como a qualidade de um produto é avaliada. Nas páginas seguintes você terá contato com aspectos da gestão da qualidade do _software_, colocada em duas diferentes perspectivas. Sigamos adiante.

_____

**➕ Pesquise mais**

Você encontrará questões interessantes sobre qualidade no artigo publicado na “[II Escola Regional de Informática da Sociedade Brasileira de Computação Regional de São Paulo – II ERI da SBC](https://www.sbc.org.br/eventos/escolas-regionais-realizadas)”.

# **Gestão da qualidade do software**

[![](https://ampli-images.s3.amazonaws.com/production/39a35bf0-efc4-4b2b-a1f8-b4aa4d98daac/original)](https://ampli-images.s3.amazonaws.com/production/39a35bf0-efc4-4b2b-a1f8-b4aa4d98daac/original)

Com a finalidade de conseguirmos um melhor aproveitamento neste tema, ficaria melhor se definirmos a gestão da qualidade como um sistema. Idealmente esse sistema de gestão da qualidade já deve estar incorporado na organização e, como se espera de qualquer sistema, ele deve incluir processos, pessoas e ferramentas dirigidas à obtenção da qualidade nas entregas.

Quando tomamos um sistema de gerenciamento financeiro ou um sistema de gerenciamento de pessoas em uma organização como exemplos, por si sós eles não deveriam demandar uma nova equipe de gerenciamento ou novos recursos. Ao contrário disso, espera-se que tais sistemas sejam partes integrantes da organização, alinhadas com necessidades particulares de finanças ou de gestão de pessoas.

De acordo com Moorthy (2013), um sistema de gestão de qualidade de _software_ deve possuir 4 níveis: o nível 1 é composto pelo manual de qualidade da empresa; o nível 2 refere-se aos métodos e processos usados pela equipe para entregar suas tarefas; o nível 3 contém as linhas principais, os checklists e os modelos, usados com bastante frequência no dia a dia e importantes na manutenção da consistência das informações e, por fim, o nível 4 refere-se aos registros e documentos usados para fins de validação de um produto, usados como evidências de uma atividade e úteis para referência futura. A figura abaixo mostra a organização dos níveis de um sistema de gestão de qualidade.

De acordo com SWEBOK (2004), publicação criada pela IEEE (Instituto de Engenheiros Eletricistas e Eletrônicos, do inglês Institute of Electrical and Electronics Engineers), o gerenciamento da qualidade de _software_ é tratado como um processo, que se aplica a todas as perspectivas de processos de _software_, produtos e recursos.

Ele define os requisitos e os responsáveis pelos processos, suas medições e saídas, além dos canais de _feedback_. O planejamento da qualidade do _software_ envolve:

- a definição do produto em termos de suas características de qualidade;
- o planejamento do processo para se obter o produto desejado.

[![](https://ampli-images.s3.amazonaws.com/production/ff66876e-765c-4bbb-ab11-efe93d9dedc0/original)](https://ampli-images.s3.amazonaws.com/production/ff66876e-765c-4bbb-ab11-efe93d9dedc0/original)

Níveis de um sistema de gestão de qualidade de software. Fonte: Moorthy (2013, p. 184).

Pois bem, um processo específico de gestão de _software_ é definido no padrão IEEE 12207.0-96 e inclui o Processo de garantia da qualidade, mais conhecido pela abreviatura SQA (_Software Quality Assurance_ ou Garantia da Qualidade do _Software_).

Esse processo – também composto por várias etapas – visa assegurar que os produtos de _software_ e os processos que os constroem estão em conformidade com os requisitos (ou funcionalidades) por meio de planejamento e execução de um conjunto de atividades destinadas a transmitir a certeza de que a qualidade é fator integrante do produto.

Isso significa que a equipe poderá se assegurar de que o problema foi clara e suficientemente compreendido e que os requisitos da solução foram definidos e expressos de forma adequada. Em relação ao processo, o papel do SQA é assegurar que tudo será implementado de acordo com o plano traçado. Desafiador, não acha?

_____

**💭 Reflita**

Sabemos que um processo de gerenciamento de qualidade tem por objetivo a tomada de providências que incluam a qualidade em todas as ações executadas durante o ciclo de desenvolvimento de um produto. No entanto, como garantir que esse processo foi concebido e aplicado corretamente? Como medir a qualidade desse processo? Em que momento a equipe poderá entender que construiu, de fato, algo de qualidade?

# **Verificação e validação**

[![](https://ampli-images.s3.amazonaws.com/production/124a94fb-d5af-4e18-a67d-a10b535f58f1/original)](https://ampli-images.s3.amazonaws.com/production/124a94fb-d5af-4e18-a67d-a10b535f58f1/original)

Outro processo que visa conferir qualidade ao produto é o que chamamos de Verificação e Validação. Para facilitar as referências ao tema, os termos verificação e validação são tratados como apenas um. De acordo com SWEBOK (2004), trata-se de um processo bem estruturado para avaliar os produtos de _software_ em todo o seu ciclo de vida, do planejamento até sua efetiva entrega.

Em resumo, retrata o esforço da equipe para garantir que a qualidade está embutida no _software_ e que ele reflete o desejo do usuário. A V&V, como também é conhecido esse processo, está interessada diretamente na qualidade do produto.

O grupo **revisões e auditorias**, nosso último processo de qualidade abordado aqui e também tratado como um único item, inclui dois principais procedimentos:

- revisões técnicas: o objetivo de uma revisão (ou análise) técnica é o de avaliar um produto de _software_ para determinar a sua adequação para a sua utilização pretendida. O objetivo é o de identificar discrepâncias a partir das especificações e dos padrões aprovados. Os resultados devem fornecer evidências que confirmem (ou não) que o produto atende às especificações;
- inspeções: o propósito de uma inspeção é detectar e identificar anomalias no _software_. Esta prática se diferencia das revisões em dois aspectos: alguém que exerça cargo de gestão sobre qualquer membro da equipe de inspeção não deverá participar desse processo, e uma inspeção deve ser conduzida por um facilitador imparcial, treinado em técnicas de inspeção.

As inspeções incluem também um líder, um responsável pelos registros da seção e um número reduzido de inspetores, comumente de 2 a 5 pessoas.

Na próxima aula, dedicada exclusivamente ao estudo da SQA e dos fatores que afetam a qualidade do _software_, você conhecerá de forma mais profunda e abrangente as providências que uma equipe pode tomar para garantir a qualidade do seu produto de _software_ e a satisfação do cliente.

Na sequência, seu desafio prático para esta aula será mais bem definido e uma solução possível lhe será indicada.

**_____**

**📝 Exemplificando**

Um bom exemplo de como um setor pode se organizar para obter _software_ de qualidade, é dado pelo caso em que determinado segmento do setor agropecuário, junto com profissionais de TI, estabeleceu um conjunto de características que foram destacadas como imprescindíveis para avaliação da qualidade de um _software_ agropecuário.

Em linhas gerais, as características eleitas foram: facilidade de uso (a interface é facilmente personalizada), facilidade de operação (é simples a entrada de dados de natureza física, zootécnica, financeira no _software_?) e integridade do sistema (o programa é capaz de manter o processamento, a despeito da ocorrência de ações inesperadas?), entre outras (ROCHA; MALDONADO; WEBER, 2001).

**_____**

**💪 Faça você mesmo**

No decorrer desta aula foi feita menção à verificação e validação como uma das providências para assegurar a qualidade do _software_. Será que V&V são atividades redundantes ou complementares? Executadas em conjunto, podem ser consideradas como teste? Em outras palavras, Verificação + Validação = Teste? Pesquise mais sobre o tema e sintetize o que aprendeu a respeito em relatório.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

As práticas ágeis implantadas na _XAX-Sooft_ têm assumido importância crescente no processo de desenvolvimento da empresa e se mostrado eficientes no aprimoramento da relação com os clientes. Sabemos que as entregas vêm sendo feitas de forma satisfatória, mas não há na _XAX-Soof_t ainda processo definido e formalizado de gerenciamento da qualidade do produto.

Isso significa que, embora os programas atendam à maioria dos requisitos estabelecidos, as providências de qualidade tomadas pela equipe durante sua construção baseiam-se muito mais na percepção subjetiva de seus membros do que em práticas e medidas objetivas e consagradas pela prática.

Neste cenário, fica muito difícil que a equipe e seus gerentes consigam estabelecer níveis aceitáveis de qualidade do produto, já que não contam com meios formais para medi-la.

Na introdução da aula foi proposto como desafio para esta aula o levantamento das práticas de qualidade atualmente implementadas na _XAX-Sooft_ e a geração de relatório contendo tal levantamento.

Uma solução possível para esse desafio é a que segue:

1. o relatório deve ser iniciado com a descrição de seu objetivo, que é o de levantar as práticas de qualidade vigentes na empresa;
2. um relato de elementos-chave da equipe deve ser colhido. Nesse relato deverá estar presente o que cada um pensa da qualidade e como a coloca em prática;
3. na sequência, o relatório deverá descrever como atualmente são feitos os testes no produto, com que frequência, em quais ocasiões e por quem;
4. por fim, o relatório deverá explicitar os pontos falhos nas investidas da equipe em favor da qualidade, tais como falta de revisões nos artefatos liberados, a frequência insuficiente na aplicação de testes e a falta de documentação adequada, por exemplo.

_____

**⚠️ Atenção**

A implantação de um processo formal de qualidade pode, num primeiro momento, transmitir a impressão de que tempo precioso de desenvolvimento está sendo desperdiçado em medições, auditorias, inspeções e práticas afins. Cabe aos líderes da equipe conscientizá-la da importância desse processo.

______

**📌Lembre-se**

Embora a maioria dos envolvidos com tecnologia da informação sejam capazes de entender a importância da qualidade, é sempre bom reforçar seu valor no processo. Leia o artigo “[Qualidade de](https://www.devmedia.com.br/qualidade-de-software/9408) [_Software_](https://www.devmedia.com.br/qualidade-de-software/9408)”.