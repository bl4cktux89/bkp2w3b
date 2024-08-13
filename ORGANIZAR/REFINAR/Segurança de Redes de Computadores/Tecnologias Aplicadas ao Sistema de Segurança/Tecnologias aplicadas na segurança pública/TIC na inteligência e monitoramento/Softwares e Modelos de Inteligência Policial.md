[![](https://ampli-images.s3.amazonaws.com/production/2a556646-260e-45fa-be2d-3906e1120f10/original)](https://ampli-images.s3.amazonaws.com/production/2a556646-260e-45fa-be2d-3906e1120f10/original)

A partir de agora vamos mergulhar em algumas aplicações de TICs em segurança pública. Veremos o papel preponderante que as mesmas estão assumindo cada vez mais na proteção a pessoas, patrimônio e recursos da nação.

Junior e Dantas (2006) mostram que a atividade de segurança pública – em especial a atividade policial – vem sendo beneficiada pelos avanços da Tecnologia da Informação. Os autores citam a mineração de dados em grandes bases de dados como grande exemplo desses avanços. Mineração esta que permite a identificação de comportamentos delitivos, o que antes da utilização de computadores e _softwares_ específicos era impossível, dado o volume intratável de dados a serem analisados (sob o ponto de vista da capacidade humana).

Este novo campo de estudos é chamado **Análise de Vínculos**, cujo objetivo é encontrar padrões de comportamento em documentação disponível publicamente sobre um indivíduo ou organização, determinando, entre estes padrões, os vínculos que, potencialmente, levarão este indivíduo ou organização a um comportamento delitivo, em futuro próximo.

Este tipo de análise se alicerça sobre a Inteligência Artificial, ramo da Ciência da Computação que se preocupa com o desenvolvimento de técnicas e métodos pelos quais os computadores possam exibir qualidades cognitivas que se assemelhem à inteligência humana (JUNIOR & DANTAS, 2006). Os autores apontam cinco áreas de desenvolvimento da Inteligência Artificial:

**Jogos por computador** – em que o sistema exiba características de aprendizado, ganhando experiência a cada partida (Xadrez, Damas, Go, entre outros).

**Sistemas especialistas** – em que os sistemas são programados para tomar decisões com base em informações prévias (sistemas de diagnóstico médico, sistemas de análise financeira em mercado de capitais, entre outros).

**Linguagens naturais** – sistemas que permitem a interação entre o ser humano e o computador em sua língua nativa, sem a necessidade de que o humano aprenda linguagens de programação ou se expresse de maneira mecânica para ser compreendido (assistentes virtuais como SIRI e Alexa, entre outros).

**Robótica** – desenvolvimento de capacidade de interação dos sistemas cibernéticos com o mundo real por meio de visão, audição e tato artificiais (novamente os assistentes artificiais, como SIRI e Alexa, entre outros)

**Redes neurais** – sistemas que simulam a inteligência humana por meio de elementos, que por sua vez simulam os neurônios e as conexões entre eles no cérebro humano. Estas redes enfraquecem ou fortalecem as conexões (ou vínculos) entre os neurônios artificiais em resposta a estímulos. Este enfraquecimento ou fortalecimento, quando estendido a toda uma rede neural, efetivamente permite que esta rede aprenda com o processo.

_____

**📝** **Exemplificando**Nos estudos de segurança pública, em especial de Criminalística, Análise de Vínculos diz respeito à capacidade de se encontrar padrões de comportamento em documentação disponível publicamente sobre um indivíduo ou organização, determinando entre estes padrões os vínculos que potencialmente levarão estes a um comportamento delitivo, em futuro próximo.

______

A metodologia da Análise de Vínculos permite que uma rede neural seja alimentada por informações de comportamento de um indivíduo ou organização cujo comportamento futuro tenha (ou não) sido delitivo. Esta última informação não é alimentada no sistema.

Os programadores da rede então perguntam se aquele conjunto prévio de comportamentos levará a algum comportamento delitivo. Após o sistema responder “sim” ou “não”, a resposta correta é inserida, o que permite que o sistema ajuste os pesos de suas conexões internas, aumentando a força daquelas que colaborariam para a resposta correta, e enfraquecendo aquelas que colaborariam para a resposta errada.

A figura a seguir ilustra uma rede neural hipotética:

[![](https://ampli-images.s3.amazonaws.com/production/8390dde1-d76a-4210-97a8-151453403339/original)](https://ampli-images.s3.amazonaws.com/production/8390dde1-d76a-4210-97a8-151453403339/original)

Uma rede neural hipotética. Fonte: elaborada pelo autor.

A figura representa uma rede neural hipotética com as seguintes características:

- **Camada de Entrada** – neste caso, formada por três nós. Cada nó da camada de entrada recebe um dado qualquer que pode, por exemplo, ser a resposta a uma pergunta afirmativa/negativa. Um exemplo: “o indivíduo em questão sofreu violência física na infância?”
- **Camada Oculta** – uma rede neural pode ter mais de uma camada oculta, é bom frisar. Esses nós ocultos representam a rede neural, simulando a interconexão de neurônios. Estes contêm o peso dos vínculos de entrada e saída, e são “treinados” para aumentar ou diminuir o peso desses vínculos.
- **Vínculos** – caminhos que ligam os nós da rede neural. Em seu conjunto, vão facilitar ou dificultar que uma resposta na camada de saída seja dada.
- **Camada de Saída** – conjunto de respostas fornecidas pela rede neural. A comparação das respostas obtidas pela rede com a resposta real gera um processo de _feedback_, que enfraquece os vínculos que gerariam a resposta errada e fortalece os vínculos que gerariam a resposta certa ao longo de toda a rede neural (isto é, envolvendo todos os vínculos).

Após vários milhares de cenários de teste, por meio dos quais o sistema é treinado, o que ocorre é que as respostas corretas vão se tornando a praxe. Quando estas respostas corretas ultrapassam algum limite determinado pelos administradores do sistema – em geral superior a 90% dos casos – o sistema é considerado adequado para uso preditivo.

______

**🔁** **Assimile**Um exemplo em que este tipo de ferramenta de inteligência policial já está sendo usado é fornecido pela British Telecom (2017). A polícia da cidade de Durham, no Reino Unido, está utilizando uma rede neural de análise de vínculos para decidir se atribui ou não liberdade condicional a detentos sob sua custódia.

O sistema funciona com base na análise de um conjunto de informações sobre o detento em questão, informações essas coletadas pelo próprio sistema judiciário de Durham (excluindo crimes e ocorrências de fora de Durham, os autores fazem questão de frisar para que tenham controle total sobre a qualidade das informações).

Com base nessas informações o sistema prevê se o detento em questão é passível de cometer outros atos delitivos mediante uma potencial liberdade condicional. O sistema é conservador, isto é, quando a probabilidade de saída é dúbia, decide por negar a condicional, uma vez que é uma questão de segurança pública. Apenas quando é claro para o sistema que o detento em questão não trará perigo para a sociedade, o detento é solto. O sistema tem as seguintes taxas de acerto altas:

- está correto em 98% dos casos em que aponta que um detento apresenta baixo risco para a sociedade;
- está correto em 88% dos casos em que aponta que um detento apresenta alto risco para a sociedade.