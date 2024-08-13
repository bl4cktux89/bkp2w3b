# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/cc2f236d-5b67-4717-b1bf-5127b8c09679/original)](https://ampli-images.s3.amazonaws.com/production/cc2f236d-5b67-4717-b1bf-5127b8c09679/original)

### **Qual é o foco da aula?**

Nesta aula, você terá contato com a base teórica sobre modalidades de teste e sobre registros de atividades no processo.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- identificar o funcionamento dos testes de unidade e integração;
- examinar os testes de usuário;
- interpretar como são elaborados os relatórios de qualidade do _software_.

**Situação-problema**

Nesta etapa do nosso estudo, já concordamos que os testes são fundamentais no processo de desenvolvimento de um produto. Sem que as devidas verificações sejam feitas, não há a mínima segurança de que o sistema se comportará conforme o esperado.

A expressão “devidas verificações” demanda atenção especial de nossa parte: ela indica, entre outras coisas, a necessidade de aplicação do teste certo, pela pessoa certa e no tempo devido.

Antes de iniciarmos a abordagem teórica, é bom que nos lembremos que temos adquirido, ao longo do curso, conhecimento das principais metodologias de desenvolvimento de _software_, das normas de qualidade e, nesta unidade, dos processos de teste de _software_. Temos como objetivo específico, nesta aula, conhecer o que são e como implementar o teste de release e o teste de usuário.

Conforme constataremos na sequência, não há apenas um tipo de teste a ser feito no produto. As verificações devem focar desde o desempenho do programa até sua adequação à máquina em que será executado. Não se pode conceber também que apenas uma pessoa ou grupo realize os testes. Diferentes pontos de vista e interesses devem ser acomodados pelo processo, fato que também deu motivo para a criação de várias modalidades de teste.

Ainda resta uma questão a ser abordada: é válido e útil o registro dos resultados obtidos no teste? Podemos considerar esses registros base para criação de histórico do processo? Desta maneira, será nesta aula que abordaremos esses assuntos que circunstanciam o processo de teste e que serão argumento para o desafio desta aula.

Novamente se faz necessário resgatarmos o desafio que dá sentido ao nosso curso: fazer com que a _XAX-Sooft_ atinja bom nível de excelência em seus processos e produtos, tendo como ponto de partida uma organização sem processo definido e sem qualquer padronização de qualidade. Em específico, nossa missão nesta aula é fazer o registro dos resultados obtidos com a aplicação do teste de _software_ como meio eficiente de formar uma base para manutenção do histórico dos processos.

Bons estudos!

# **Testes de unidade e de integração**

[![](https://ampli-images.s3.amazonaws.com/production/1d886edd-f1cf-42ab-b190-286d1e08c781/original)](https://ampli-images.s3.amazonaws.com/production/1d886edd-f1cf-42ab-b190-286d1e08c781/original)

Para entender um teste de unidade, imagine o _software_ como um conjunto de partes que, juntas, formam o todo. Essa modalidade de teste é direcionada a uma rotina, classe ou pequena parte de um produto e é normalmente executada pelo próprio desenvolvedor, de modo a assegurar que determinada unidade poderá ser integrada ao resto do _software_.

No contexto dos testes de unidade (ou testes unitários) insere-se um elemento conhecido como stub. Ele simula resultados que são retornados por um determinado componente do qual o _software_ depende (PINHEIRO, 2015). Em outras palavras, um stub é um trecho de código que substituirá as entradas, dependências e comunicações que a unidade deveria receber em uma execução do programa. Quando um componente A que vai ser testado chama operações de outro componente B que ainda não foi implementado, pode-se criar uma implementação simplificada de B, chamada stub. Neste caso, devemos entender que o componente A é a unidade a ser testada.

_____

**📝 Exemplificando**

Veja um bom exemplo de aplicação de um stub: Suponha que o componente A é uma classe que deve usar um gerador de números primos B. A implementação de B ainda não foi feita. No entanto, para testar a unidade A não será necessária a geração de alguns poucos números primos. Assim, B pode ser substituído por uma função stub que gera apenas os 5 primeiros números primos (WAZLAWICK, 2013).

_____

Há situações, no entanto, em que o módulo B já está implementado, mas o módulo A (que aqui representa nossa unidade) que chama as funções de B ainda não foi implementado. Deverá ser implementada, então, uma simulação do módulo A, que recebe o nome de driver. A diferença entre stubs e drivers concentra-se na relação de dependência entre os componentes. As técnicas de teste funcional e estrutural, ambas abordadas anteriormente nesta unidade, podem ser utilizadas para a execução de um teste de unidade.

O teste funcional serve para validar a função específica que está sob teste. Quando utilizada, a técnica de teste estrutural (ou caixa-branca) viabiliza a validação dos fluxos de execução da unidade. Ambas as técnicas podem ser utilizadas de forma combinada ou isolada num teste de unidade.

_____

**💭 Reflita**

Os stubs, como sabemos, geram valores de entrada para unidades que serão testadas. Você entende como legítimo que um stub seja construído também para gerar valores errados para a classe, por exemplo?

_____

**Testes de integração**

Trata-se de teste executado pelo testador para garantir que vários componentes do sistema funcionem corretamente juntos (PINHEIRO, 2015). Eles são feitos quando as unidades (as classes, por exemplo) já foram testadas de forma isolada e precisam ser integradas para gerar uma nova versão do _software_.

No caso de as classes a serem testadas precisarem de comunicação com outros componentes ou classes que ainda não foram testadas – ou mesmo implementadas –, os stubs mais uma vez serão necessários. O problema com um stub é que se investe tempo para desenvolver uma função que não será efetivamente entregue. Além disso, nem sempre é possível saber se a simulação produzida pelo stub será suficientemente adequada para os testes (WAZLAWICK, 2013).

Com o sistema integrado e testado, chega o momento de entregá-lo ao usuário para que ele o teste também.

# **Teste de usuário (ou teste de aceitação)**

[![](https://ampli-images.s3.amazonaws.com/production/a358e96b-c2e9-4cde-b567-c110e5b01545/original)](https://ampli-images.s3.amazonaws.com/production/a358e96b-c2e9-4cde-b567-c110e5b01545/original)

Quando já se dispõe da interface final do sistema, o teste de aceitação já pode ser aplicado. Como o próprio nome nos faz supor, esse teste é executado pelo usuário e não pela equipe de testadores ou desenvolvedores. Para entendermos melhor essa modalidade de teste, é interessante que a coloquemos em oposição ao teste de sistema.

O **teste de sistema** é feito quando todas as unidades e as integrações entre elas já foram testadas. Pode ser que a equipe já se sinta confiante o bastante nesse ponto para assumir que seu produto é de boa qualidade. No entanto, é necessário que ele passe por esse novo teste depois de integrado. O objetivo da sua aplicação é o de verificar se o programa é capaz de executar processos completos, sempre adotando o ponto de vista do usuário.

Pois bem, o teste de usuário pode ser planejado tal qual o teste de sistema. A diferença é que ele será executado pelo usuário. Em outras palavras, enquanto o teste de sistema faz a _verificação_ do sistema, o teste de aceitação faz sua _validação_.

_____

**📝 Exemplificando**

Um plano viável para a realização de teste de aceitação em um programa de vendas pela internet é o que segue no quadro abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/093065d1-cb3a-48ec-b58e-c9c2f146eff2/original)](https://ampli-images.s3.amazonaws.com/production/093065d1-cb3a-48ec-b58e-c9c2f146eff2/original)

Exemplo de roteiro para teste de aceitação. Fonte: adaptado de Wazlawick (2013, p. 296).

_____

O teste de aceitação é chamado de **Teste Alfa** quando feito pelo cliente sem planejamento rígido ou formalidades. Se o teste é ainda menos controlado pelo time de desenvolvimento e as versões do programa são testadas por vários usuários, sem acompanhamento direto ou controle da desenvolvedora, então o procedimento é chamado de **Teste Beta**. Nesta modalidade, as versões disponibilizadas costumam expirar depois de certo tempo de uso.

______

**🔁 Assimile**

O teste de aceitação visa à validação dos requisitos implementados no _software_, não mais a verificação de defeitos (WAZLAWICK, 2013).

______

Um termo bastante comum no contexto dos testes de aceitação é o _release_. Literalmente, o termo refere-se a uma liberação ou lançamento de uma nova versão de um produto de _software_. Os testes aplicados sobre um release seguem o padrão dos testes de usuário. Usualmente, um lançamento obedece às seguintes fases:

- alfa: nesta fase, o lançamento ainda está em processo de testes, que são realizados por pessoas situadas normalmente fora do processo de desenvolvimento. Os produtos em fase de teste alfa podem ser instáveis e sujeitos a travamento.
- beta: trata-se da classificação posterior a Alfa. Um lançamento em beta teste é avaliado por testadores beta, normalmente clientes em potencial que aceitam a tarefa de teste sem cobrar por isso. Uma versão Beta é utilizada para demonstrações dentro da organização e para clientes externos.
- _Release Candidate_: trata-se de versão do sistema com potencial para ser a versão final. Neste caso, todas as funcionalidades já foram devidamente testadas por meio das fases Alfa e Beta.

Um _release_ pode ser interno ou externo. O primeiro é usado somente pela equipe interna de desenvolvimento para fins de controle ou para demonstração a clientes e usuários. Um release externo é uma versão do produto distribuída para os usuários finais (BARTIÉ, 2002).

De uma forma ou de outra, as modalidades de teste apresentadas até aqui relacionam-se diretamente às funcionalidades do sistema. Em outras palavras, elas fazem a verificação dos processos que efetivamente devem ser realizados pelo programa. No entanto, a abrangência dos testes é maior e demanda a aplicação de outros tipos de verificações no produto. A esses tipos damos o nome de testes suplementares. Vejamos dois exemplos a seguir.

a) **Teste de Desempenho**: tipo que tem por objetivo determinar se, nas situações de pico máximo de acesso e concorrência, o desempenho ainda permanece consistente com o que foi definido para essa característica do sistema. Assim, o critério de sucesso aqui é a obtenção de tempo de resposta compatível com o que se espera do produto, quando o sistema trabalha em seu limite. Um plano possível para esse teste está descrito a seguir (BARTIÉ, 2002):

- validar todos os requisitos de desempenho identificados;
- simular n usuários acessando a mesma informação, de forma simultânea;
- simular n usuários processando a mesma transação, de forma simultânea;
- simular n% de tráfego na rede;
- combinar todos esses elementos.

Quando o procedimento eleva ao máximo a quantidade de dados e transações às quais o sistema é submetido, o teste realizado é chamado de **Teste de Estresse**. Ele é realizado para que se possa verificar se o sistema é suficientemente robusto em situações extremas de carga de trabalho.

b) **Teste de recuperação**: seu objetivo é avaliar o _software_ após a ocorrência de uma falha ou de uma situação anormal de funcionamento. Algumas aplicações demandam alta disponibilidade do programa e, no caso de falha, o _software_ deve ter a capacidade de se manter em execução até que a condição adversa desapareça.

Os testes de recuperação devem prever também os procedimentos de recuperação do estado inicial da transação interrompida, impedindo que determinados processamentos sejam realizados pela metade (BARTIÉ, 2002).

Normalmente, o teste de recuperação trata de situações referentes a (WAZLAWICK, 2013):

- queda de energia na organização em que o sistema está em funcionamento;
- discos corrompidos;
- problemas de queda de comunicação;
- quaisquer outras condições que possam provocar a terminação anormal do programa ou a interrupção temporária em seu funcionamento.

_____

**➕ Pesquise mais**

É possível que, ao se aplicar uma manutenção num programa, outros defeitos sejam gerados no código? Acertou se respondeu que sim. Leia o artigo “[_A importância dos testes de regressão_](http://gtsw.blogspot.com/2009/03/importancia-dos-testes-de-regressao.html)”.

_____

Pois bem, eis então algumas das outras modalidades de teste e outros conceitos relacionados à atividade. Chega a hora, então, de tratarmos dos registros das atividades de teste, visando capacitá-lo ainda mais para o desafio desta aula. Vamos a eles?

# **Os relatórios da qualidade do software**

[![](https://ampli-images.s3.amazonaws.com/production/8ac004b7-fc36-4ba4-96a6-6508a2cc32bb/original)](https://ampli-images.s3.amazonaws.com/production/8ac004b7-fc36-4ba4-96a6-6508a2cc32bb/original)

O registro das atividades relacionadas ao processo de qualidade, sobretudo os testes, são feitos em relatórios específicos. Além do efetivo registro, eles servem também como instrumentos de medição e análise. A execução do teste deve gerar o que chamamos de log, que nada mais é do que o registro das atividades desempenhadas. Vamos a alguns deles:

- log de execução: este documento é criado para registrar todos os procedimentos realizados durante a execução de um ciclo de testes, bem como apontar as eventuais interrupções ocorridas. O log de execução certifica que, de fato, o teste foi realizado.
- ocorrências da validação: neste documento registram-se todas as ocorrências geradas durante um teste. Uma ocorrência pode ser, por exemplo, a identificação de um defeito. Neste caso, alguns dos dados a serem relatados serão: um nome ou número de identificação do defeito, a data em que foi encontrado e a sequência de ações capazes de reproduzi-lo (BARTIÉ, 2002).

Um dado também bastante importante a ser registrado é a classificação do defeito. Apesar de haver muitas classificações, alguns deles são mais relevantes:

a) **falha na descrição funcional**: esta classificação refere-se à discrepância entre a descrição da funcionalidade e sua efetiva implementação. Por exemplo: a descrição da funcionalidade estabelece que o programa deveria promover acréscimo trimestral automático do salário dos gerentes de seção e o sistema aplica o aumento a cada quatro meses;

b) **falha no controle, lógica ou sequenciamento do algoritmo**: um laço de repetição infinito é um exemplo desse tipo de falha;

c) **falha nas estruturas de dados:** trata-se da definição incorreta, por exemplo, de matrizes e tabelas de banco de dados;

O relatório de teste, em resumo, serve para registrar a maior quantidade possível de dados acerca do processo.

_____

**💪 Faça você mesmo**

A norma IEEE 829 é o padrão criado pela IEEE para documentação do processo de teste. Um dos relatórios recomendados pelo padrão é o de incidente de teste, que prevê a descrição dos seguintes itens, entre outros, em caso de ocorrência de um incidente: entradas, resultados esperados e resultados encontrados. Vale registrar que um incidente pode ser entendido como discrepância entre o resultado esperado e o encontrado na execução dos casos de teste.

Crie um exemplo de um processo de teste que contemple uma entrada de caso de teste, faça previsão de um resultado esperado para aquela entrada e forneça a descrição do resultado obtido.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)

A caminhada da _XAX-Sooft_ rumo à excelência não para! Depois de fazer a seleção dos casos de teste e de efetivamente aplicar teste funcional em um dos seus produtos, a _XAX-Sooft_ vê-se na necessidade de fazer um registro criterioso das atividades desempenhadas no processo de teste, com a finalidade de criar base de comparação para testes futuros. Afinal, como saber se a aplicação de um método foi bem-sucedida se não pela comparação entre dois ou mais resultados?

Vale a pena dizer que, na prática, os registros dos resultados obtidos no teste são feitos no ato da sua aplicação ou em situação inserida em seu contexto. Por exemplo, as anotações referentes à ocorrência de uma falha no algoritmo devem ser feitas assim que ela acontece, no momento do teste. Para efeito de organização didática, esta aula coloca o registro das ocorrências e resultados como etapa posterior à aplicação do teste, embora não o seja de fato.

Pois bem, o desafio lançado aqui é justamente o de registrar o processo e os resultados obtidos com a aplicação do teste de _software_ em um dos seus produtos. O que deve ser registrado? O que não deve ser registrado? Há formato definido? Uma solução possível para esse desafio é a seguinte:

- A equipe deve criar, oficializar e publicar um log de execuções, ou seja, um formulário apropriado para que todos os registros de ocorrências sejam feitos;
- O formulário de registro deve conter, no mínimo, os seguintes campos:

1. responsáveis pelo teste;data e horário de início;data e horário de término; função, unidade ou sistema testados; fase do teste: teste de unidade, teste de integração ou teste de sistema; falha na interpretação da função: nesta seção devem ser relatadas as divergências entre a função especificada nos requisitos e a função de fato implementada; falha na construção de estrutura de dados: erros na criação de tabelas e outras estruturas devem ser registrados aqui; defeito algorítmico: devem ser identificados erros de lógicas, laços infinitos, por exemplo;travamento de origem não identificada; outras ocorrências relevantes.

Esse formulário pode – e deve – passar por constante aprimoramento em seus campos e em sua utilização.

_____

**⚠️ Atenção**

O formato do _log_ de execuções é livre e deve ser definido pela equipe, segundo critérios próprios.

______

**📌Lembre-se**

A norma IEEE 829 é o padrão criado pela IEEE para documentação do processo de teste.