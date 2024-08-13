# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/45c099af-c9ec-4242-8e97-0623d19d2e39/original)](https://ampli-images.s3.amazonaws.com/production/45c099af-c9ec-4242-8e97-0623d19d2e39/original)

### **Qual é o foco da aula?**

Nesta aula, você terá embasamento para perceber a manutenção de forma diferente e poderá ter contato com um meio de dimensionar o esforço que deverá ser exigido para a conclusão de uma atividade de manutenção.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- identificar a manutenção como atividade fundamental no ciclo de vida do _software_;
- examinar como ocorre a manutenção pós-entrega;
- esclarecer como é feito o relatório de defeitos e a estimação de esforço e manutenção.

**Situação-problema**

Aqui estamos, em nossa última aula. No trajeto que se iniciou pelo desenvolvimento de produtos com base apenas no talento individual dos seus desenvolvedores até o atingimento da maturidade processual, a _XAX-Sooft_ percorreu um longo caminho.

Assim que constatou a necessidade de organizar seus processos, a empresa adotou e consolidou metodologia consagrada de desenvolvimento de _software_ e, no momento seguinte, enxergou a necessidade de evoluir para um modelo ágil e moderno de criação de programas. Ato contínuo, passou a adotar medidas e padrões de qualidade com fins de atingir a excelência em seus produtos. Por fim, como parte do esforço para aprimoramento da qualidade, implantou procedimento formal de testes. Você, claro, foi figura fundamental nessa transformação.

Este é o retrato da _XAX-Sooft_ atual: uma empresa sólida, reconhecida em seu meio, amadurecida em seus processos e preocupada com sua constante evolução. E é justamente de evolução que trata esta última aula. Como meio de completar seu ciclo virtuoso de desenvolvimento, a organização pretende adotar meios eficientes de manutenção dos seus produtos e implantar modelo para estimar o esforço que esta atividade acarretará à equipe.

Em resumo, o objetivo desta aula é abordar a manutenção e a evolução do _software_ e o desafio que se propõe é justamente implantar um modelo de estimação de esforço de manutenção num dos produtos da _XAX-Sooft_. Com essa medida, a manutenção deixará de ser encarada como um retrabalho e passará a ser tida como meio de proporcionar evolução ao produto.

Por fim, nesta última aula, vale a pena resgatarmos as competências que motivaram nosso estudo até aqui. Parabéns pelo bom trabalho feito até aqui e vamos em frente!

# **A manutenção pós-entrega**

[![](https://ampli-images.s3.amazonaws.com/production/7c056830-4b5b-4c0e-a031-b1be1068a7e0/original)](https://ampli-images.s3.amazonaws.com/production/7c056830-4b5b-4c0e-a031-b1be1068a7e0/original)

A expressão manutenção de _software_, quando entendida da forma costumeira, remete apenas a correções no programa provocadas pela ocorrência de erros durante a operação feita pelo usuário final. No entanto, essa atividade pode e deve assumir caráter mais significativo do que o meramente corretivo. Ao mudar sua concepção sobre a atividade, a equipe poderá colocar-se diante da oportunidade de fazer o produto evoluir sem fazê-lo perder suas características principais, o que certamente terá boa consequência na utilidade do produto e na satisfação do cliente.

Assim que o produto passa pelo teste de aceitação, ele está apto a ser entregue ao cliente. Embora longe de ser considerada o encerramento definitivo do ciclo do _software_, a entrega marca o término do desenvolvimento de uma versão apta a ser utilizada em meio produtivo e adequada ao propósito de resolver as situações colocadas pelo cliente como requisitos do produto. Esse marco no processo caracteriza-se também por ser o ponto de início de outra etapa igualmente desafiadora: a manutenção pós-entrega.

Hoje em dia, a expressão “manutenção de _software_” vem sendo substituída ou usada em conjunto com “evolução de _software_”. Evolução talvez seja o termo mais adequado, já que as atividades de modificação de um produto que já está em operação não visam mantê-lo em seu estágio atual, mas fazê-lo evoluir de forma a adaptar-se a novos requisitos ou ainda corrigir defeitos (WAZLAWICK, 2013). Usaremos aqui as duas expressões como sinônimas.

_____

**💭 Reflita**

É correto imaginar que, após seu desenvolvimento, um _software_ terá seu valor diminuído com o passar do tempo? Se imaginou que sim, está correto. Conforme falhas são descobertas no programa, conforme seus requisitos originais mudam e conforme produtos menos complexos, mais eficientes e mais avançados são lançados, o valor (não necessariamente financeiro) do _software_ original vai se perdendo. Daí a necessidade de se aplicar melhorias que façam o produto evoluir.

_____

Existem basicamente três razões que justificam o investimento na aplicação de modificações em um produto:

- uma falha de compreensão de um requisito, de projeto, codificação, de documentação ou de qualquer outro tipo deve ser corrigida. Tal ação configura uma **manutenção corretiva**.
- quando o código ou outro artefato é modificado para que a eficiência do produto aumente, temos uma **manutenção de aperfeiçoamento, ou perfectiva**.
- se o programa deve se adaptar a uma mudança no ambiente em que ele opera (uma mudança na quantidade de dígitos das linhas telefônicas, por exemplo), então ocorre uma **manutenção adaptativa** (SCHACH, 2008).

É saudável que toda iniciativa de manutenção passe pela avaliação de viabilidade em se aplicar modificações em um programa ou se construir um novo produto. Fatores como dificuldades técnicas na manutenção, inadequação do produto original às necessidades do cliente e custo devem ser levados em conta antes da decisão.

_____

**📝 Exemplificando**

A diferença entre a necessidade de novo desenvolvimento e a necessidade de aplicação da manutenção em produto já existente pode parecer clara, mas vale a pena contrastarmos as duas situações, considerando outros fatores que não o aspecto técnico apenas. Leia com atenção o que segue.

Imagine que uma mulher teve seu retrato pintado aos 18 anos. Anos mais tarde, já casada, ela decide que o marido deve ser incluído no quadro, ao seu lado. Grandes dificuldades acompanham essa decisão:

- a tela não é grande o suficiente para acomodar o marido ao lado dela;
- com o tempo, as cores do quadro ficaram menos vivas. Haveria possibilidade de retoque, mas a tinta usada já não é mais fabricada;
- o artista original se aposentou e foi morar em outro país;
- o rosto da mulher envelheceu e não há garantia de que a figura do quadro possa ficar parecida com a feição atual da mulher.

Considere agora a manutenção de um programa de computador que custa R$ 2 milhões para ser desenvolvido. Quatro dificuldades se apresentam:

- o disco rígido no qual a base de dados está armazenada está quase cheio e novos dados não podem mais ser incluídos;
- a empresa que fabricava o disco faliu e outro disco de maior capacidade, de outro fabricante, já foi comprado. No entanto, há incompatibilidade entre o novo disco e o _software_ e as adequações custarão R$ 100 mil;
- os desenvolvedores originais já se aposentaram e a manutenção deverá ser feita por profissionais que jamais cuidaram do programa antes;
- o produto original foi construído por meio do uso do modelo clássico de desenvolvimento. No entanto, há real necessidade de que o paradigma de orientação a objeto seja usado no produto que surgirá depois da manutenção.

Percebe a correspondência entre os itens do quadro e os itens do programa? A conclusão para o primeiro caso é que, partindo da estaca zero, um outro artista deverá pintar o retrato do casal para atender ao pedido da mulher. Isso também significa que, ao invés da manutenção de R$ 100 mil, um novo produto de R$ 2 milhões deve ser criado? Independentemente de estarmos tratando de quadros ou de programas de computador, muitas vezes parecerá mais simples e viável a criação de um novo produto. No entanto, considerações financeiras podem tornar a manutenção muito mais imediata do que um novo desenvolvimento (SCHACH, 2008).

_____

Por mais improvável que possa parecer, a manutenção pós-entrega consome mais tempo e recurso do que qualquer outra atividade do ciclo do produto.

Atualmente, aproximadamente dois terços do custo total de um programa estão relacionados à manutenção (SCHACH, 2008). A figura abaixo mostra a relação de custos entre atividades de desenvolvimento e manutenção em dois momentos passados.

[![](https://ampli-images.s3.amazonaws.com/production/f12df872-6bf2-4ce4-aec8-22c666992ef0/original)](https://ampli-images.s3.amazonaws.com/production/f12df872-6bf2-4ce4-aec8-22c666992ef0/original)

Relação entre custo e manutenção entre 1976 e 1981 x Relação entre custo e manutenção entre 1992 e 1998. Fonte: Schach, 2008.

Fica claro que o investimento em técnicas, ferramentas e boas práticas que levem à redução desse custo se justifica plenamente. Uma dessas boas práticas é a incorporação da facilidade de manutenção do produto desde o início do seu desenvolvimento, por meio da correta modularização do produto e das atividades de verificação e validação desempenhadas durante todo o processo.

A correção de um erro apontado pelo usuário final demanda conhecimento não só do código-fonte, mas de todos os demais aspectos relacionados à sua produção, tais como as especificações dos requisitos, o projeto e a documentação relacionada.

**______**

**🔁 Assimile**

Já que o produto de _software_ é formado por outros elementos além do código-fonte, qualquer alteração nos manuais feita após a entrega pode ser considerada manutenção.

# **Relatório de defeitos**

[![](https://ampli-images.s3.amazonaws.com/production/2b009662-15dd-4082-8e71-22f65b83d539/original)](https://ampli-images.s3.amazonaws.com/production/2b009662-15dd-4082-8e71-22f65b83d539/original)

Na segunda aula estudamos tratamentos possíveis para erros no programa descobertos durante seu processo de desenvolvimento. Embora estejamos tratando agora de um programa já entregue, não haveria motivo relevante o suficiente para nos fazer mudar o fluxo para correção do erro neste atual contexto.

Como qualquer atividade desenvolvida durante a criação de um produto de _software_, a manutenção também requer processo formal e gerenciamento. Um elemento bastante importante neste gerenciamento é o **relatório de defeitos**. Via de regra, ele é preenchido pelo usuário final e contém informações suficientes para permitir que o programador de manutenção recrie o problema descoberto pelo cliente. Confirmada a existência do erro, o programador poderá classificá-lo como crítico, importante, normal, secundário e trivial, conforme sua relevância (SCHACH, 2008).

_____

**📝 Exemplificando**

Se um programa usado para folha de pagamento apresenta erro um dia antes da data do cálculo dos salários dos funcionários, então estaremos diante de um erro crítico e a intervenção da equipe deverá ser imediata.

_____

Há, no entanto, a possibilidade de o usuário final ter interpretado mal um item do manual do produto e, por isso, entendido que determinada situação relacionada a ele se tratava de um erro. Neste caso, ao invés de correção, cabe apenas esclarecimento.

Suponhamos que o programador de manutenção tenha constatado a anomalia no programa. Ele deverá iniciar, então, a correção, sempre tomando precaução para que o processo não acabe introduzindo novos erros.

______

**🔁 Assimile**

A inclusão ou alteração de uma função ou módulo no sistema requer a execução de **testes de regressão**, que visam evitar erros de integração com os módulos originais do sistema.

______

Feita a correção, o programador (ou outro membro da equipe) deverá realizar novo processo de teste, objetivando assegurar que o problema original foi sanado e nenhum outro foi criado em decorrência do ajuste.

São claras, portanto, as semelhanças entre o processo de correção de um erro antes da entrega do programa e o processo de correção desenvolvido após a entrega. No primeiro caso, entretanto, o testador é o responsável principal pela descoberta do erro. No segundo, o próprio usuário final o encontrará.

______

**📌Lembre-se**

Já que o produto de _software_ é formado por outros elementos além do código-fonte, qualquer alteração nos manuais feita após a entrega pode ser considerada manutenção.

______

Pois bem, parece-nos claro agora que a manutenção é atividade fundamental no ciclo de vida do _software_ e que, dada a sua contribuição para o aprimoramento constante do produto, ela justifica plenamente ser chamada de evolução do _software_.

Em que pese sua importância no processo, há que se pensar no esforço necessário para empreender tal atividade. Afinal, como você pode imaginar, investimento em recursos humanos e financeiros sempre serão necessários.

Na sequência, será abordado um modelo de estimação de esforço de manutenção. Através da aplicação dessa técnica, você poderá quantificar qual o trabalho previsto para a atividade, com base na porcentagem de linhas de código que sofrerão alteração.

# **ACT - Modelo de Estimação de Esforço de Manutenção**

[![](https://ampli-images.s3.amazonaws.com/production/2a02404a-3e05-49c3-bbd3-2841d667ad2d/original)](https://ampli-images.s3.amazonaws.com/production/2a02404a-3e05-49c3-bbd3-2841d667ad2d/original)

O modelo ACT (_Annual Change Traffi_c ou Tráfego Anual de Mudança) foi proposto por Boehm (1981) e se baseia em uma estimativa de porcentagem de linhas de código que passarão por manutenção. Para efeito de contagem, são consideradas como linhas em manutenção tanto as linhas a serem alteradas quanto as novas linhas criadas. O valor da variável ACT reflete o número de linhas que sofrem manutenção dividido pelo número total de linhas do código em um ano típico (WAZLAWICK, 2013).

A fórmula criada é E = ACT * SDT, em que E representa o esforço, medido em desenvolvedor/mês, a ser aplicado no período de um ano nas atividades de manutenção, ACT representa a porcentagem esperada de linhas modificadas ou adicionadas durante um ano em relação ao tamanho do _software_ e SDT é o tempo de desenvolvimento do _software_, ou _Software Development Time_.

_____

**➕ Pesquise mais**

Entre os anos de 1974 e 1996, o pesquisador alemão Meir M. Lehman publicou oito leis que colocam a evolução do _software_ como necessária e inevitável. Você pode pesquisar sobre o tema lendo os textos abaixo:

- “[_Manutenção de software_](http://www.rafaeldiasribeiro.com.br/downloads/testesw5.pdf)”
- “[Dinâmica da Evolução (Leis de Lehman)](https://homepages.dcc.ufmg.br/~figueiredo/disciplinas/aulas/evolucao-leis-lehman_v01.pdf)”

_____

Como exemplo, se tomarmos um programa que foi desenvolvido com o esforço de 80 horas de desenvolvimento/mês, seu SDT será igual a 80. Se a taxa anual esperada de linhas em manutenção (ACT) for de 2%, então o esforço anual esperado de manutenção para esse programa será dado por E = 0,02 * 80; E = 1,6.

De acordo com essa técnica, espera-se um esforço anual de 1,6 horas de desenvolvimento/mês destacadas para atividade de manutenção (WAZLAWICK, 2013).

É claro que você deve considerar a criticidade da manutenção, a experiência dos programadores, a complexidade do programa e outros fatores que poderão influenciar na necessidade de mão de obra. Contudo, não se pode negar que essa estimativa irá te ajudar a ter boa noção da quantidade de programadores que deverá destacar para a atividade.

Pois bem, chegamos ao fim do nosso conteúdo. Torcemos vivamente para que a compreensão dos assuntos abordados tenha sido satisfatória e que o conhecimento adquirido seja decisivo na realização do seu projeto de vida. Fica a seguinte sugestão: não pare por aqui! A Engenharia de _Software_ é um campo vastíssimo e tópicos mais avançados desta disciplina devem merecer sua atenção.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/add8528f-cdc3-4eb4-8b7c-dd722eb0c857/original)](https://ampli-images.s3.amazonaws.com/production/add8528f-cdc3-4eb4-8b7c-dd722eb0c857/original)

Não nos enganemos: a manutenção é uma daquelas atividades que apresentam grandes desafios em sua execução e que não conferem grande reconhecimento a quem as pratica. Não é incomum que programadores sem muita experiência ou sem grande capacidade técnica sejam destacados para cuidar dos ajustes em um programa. Isso, contudo, está longe de diminuir sua importância.

É por meio da manutenção que o programa se torna mais adequado à sua função, mais confiável, melhora seu desempenho e ganha inovações interessantes. Claro que tudo isso tem seu custo, tanto material, quanto relacionado à mão de obra. Sob essa perspectiva, é natural que uma organização queira fazer estimativas de quanto esforço deverá ser empreendido na atividade e, com elas, dimensionar seu investimento.

Depois de adotar as medidas de qualidade necessárias para o atingimento de nível satisfatório de excelência, a atenção da _XAXSooft_ volta-se agora justamente para um meio de estimar o esforço que empreenderá em suas manutenções. A métrica a ser adotada é de aplicação bem simples e a apuração de seu resultado servirá para parametrizar as decisões relacionadas à atividade.

A maneira que se propõe para a resolução do desafio é igualmente simples. Imaginemos um programa relativamente complexo da _XAXSooft_ que tenha sido desenvolvido com o esforço de 100 horas de desenvolvimento no mês. Por causa da complexidade das suas funções, a taxa esperada de linhas que passarão por manutenção é de 6%.

Aplicando esses valores na fórmula _E = ACT * SDT_, teremos que:

_E = 0,06 * 100_

Espera-se, então, um esforço anual de 6 horas de desenvolvimento por mês, no intervalo de 12 meses.

_____

**⚠️ Atenção**

Existem outras técnicas importantes de estimativa de esforço de manutenção. Uma delas leva o nome de CII.

# **Referências bibliográficas**

[![](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)

BARTIÉ, A. **Garantia da qualidade de** _**software**_: as melhores práticas de engenharia de _software_ aplicadas à sua empresa. 5. ed. São Paulo: Elsiever, 2002.

DELAMARO, M. E. **Introdução ao teste de** _**software**_. Rio de Janeiro: Elsevier, 2004.

MECENAS, I.; OLIVEIRA, V. **Qualidade em** _**software**_: uma metodologia para homologação de sistemas. [S. l.]: Alta Books, 2005.

MOORTHY, V. _**Jumpstart to software quality Assurance**_. [S.l : s.n.], 2013.

PINHEIRO, V. Um comparativo na execução de testes manuais e testes de aceitação automatizados em uma aplicação web. Simpósio Brasileiro de Qualidade de _Software_ – SBQS 2015. **Anais**... Manaus: Uninorte, 2015.

PRESSMAN, R. S. **Engenharia de** _**software**_. São Paulo: Pearson Prentice Hall, 2009.

ROCHA, A. R.; MALDONADO, J. C.; WEBER, K. C. **Qualidade de** _**software**_: teoria e prática. São Paulo: Pearson, 2001.

SCHACH, S. **Engenharia de** _**software**_: os paradigmas clássico e orientado a objetos. 7. ed. São Paulo: McGraw-Hill, 2008.

SHAFFER, Steven C. _**A brief introduction to software development and quality assurance management**_. [S.l : s.n.], 2013.

WAZLAWICK, R. S. **Engenharia de** _**software**_: conceitos e práticas. Rio de Janeiro: Elsiever, 2013.