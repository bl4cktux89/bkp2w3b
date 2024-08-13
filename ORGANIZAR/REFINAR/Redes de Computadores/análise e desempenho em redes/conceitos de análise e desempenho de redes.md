### Introdução

Com a grande expansão da internet e a popularização das redes de computadores, vários serviços que antes não existiam passaram a existir e utilizar a rede, compartilhando informações que cada vez mais, são essenciais para os negócios. Entender o que se passa nas redes de computadores local ou mundial é um fator de sucesso para melhorar o desempenho nas comunicações globais.

Uma rede de computadores segundo Kurose (2006) é uma estrutura complexa que requer atenção por possuir muitos detalhes, sendo assim, os seus elementos devem ser conhecidos e qualquer modificação ser cuidadosamente planejada.  Devido a esta complexidade e a grande gama de serviços disponíveis conforme Subraya (2006), o desempenho na rede de computadores pode ser seriamente afetado, implicando muitas vezes em lentidões excessivas ou perda de serviços.

A infraestrutura que suporta a internet por sua vez é formada por diferentes tipos de hardware, como servidores, estações, dispositivos de armazenamento, LANs, WANs, balanceadores de carga, otimizadores de trafego, roteadores e entre outros e todos estes elementos são fatores que influenciam diretamente o desempenho dos sistemas e das redes de comunicação (SUBRAYA, 2006). Os vários tipos de processos de software compartilham esses recursos gerando atrasos e esperas, formando assim as filas. Uma requisição na web utiliza parte de seu tempo recebendo serviços dos diferentes hardwares da rede, consumindo recursos de outras partes nestas filas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/9/269998/13099.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/9/269998/13099.jpg)

Pode-se definir desempenho como sendo a maneira de atuar ou de se comportar de alguém ou algo, avaliada em termos de rendimento e/ou eficiência, sendo assim o desempenho é uma medida relativa a um conjunto de índices aferidos experimentalmente que define o alcance ideal ou pré-definido de algo, mesmo que não seja ideal, mas serve como referência para a medição do desempenho.

### **Entendendo melhor a noção de desempenho**

Para entender melhor a questão do desempenho, veja, por exemplo, o caso de uma agência bancária.  Analisando o cenário percebe-se que existem alguns objetos básicos, como computadores, operadores de caixa e clientes.  O objetivo principal é o atendimento ao cliente em tarefas como saques, depósitos, transferências, extratos, pagamento de contas, etc., de forma eficiente. Pela experiência pessoal de cada um, chega-se a uma conclusão lógica, que um bom atendimento deverá ser:

- Rápido.
- Com pequenas filas.
- Com muitos pontos de atendimento (caixas).

Logo, pode-se concluir que com uma grande quantidade de pontos de atendimento, as filas serão pequenas com escoamento mais rápido, porém alguns caixas em horários de menor movimento ficarão ociosos, gerando custos à agência bancária, que no final repassará estes custos ao cliente. Neste caso, o mais interessante é maximizar o custo–benefício. Para isso, é necessário fazer um dimensionamento do número ideal de atendentes de caixa. Portanto, é importante saber, por exemplo, quantos caixas são necessários para garantir um tempo de espera máximo de 15 minutos e o que pode influenciar essa medida de desempenho.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/9/354959/24092.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/9/354959/24092.png)

Agencia Bancaria

Outro exemplo importante onde uma análise no desempenho é fundamental e o caso dos caixas de atendimento de um hipermercado. Pode-se observar que existe os caixas rápidos para pessoas que possuem poucos produtos em seus carrinhos, por exemplo até 20 itens, caixas dedicadas para atendimento de idosos e gestantes, e caixas para carrinhos com bem mais de 20 itens. Neste caso alguns fatores que podem influenciar na lentidão no atendimento poderiam ser:

1. Quantidades de caixas nas filas rápidas.
2. Quantidade de caixas nas filas para idosos e gestantes.
3. Quantidade de caixas com carinhos cheios.
4. Dias do mês, perto do pagamento a ida aos mercados costuma aumentar.
5. Promoções exclusivas.
6. Feriados especiais - dia das mães, namorados, natal, etc.

Sendo assim o dimensionamento das filas é influenciado por uma série de fatores que devem ser levados em consideração para manter um bom atendimento. Como podemos ver o desempenho de qualquer sistema está diretamente relacionado com os recursos disponíveis, bem como as demandas do público, entre outras que poderíamos levantar.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/6/1/16144/shutterstock_128231780.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/6/1/16144/shutterstock_128231780.jpg)

Caixa de mercado

### Fatores essenciais no desempenho em rede de computadores

Nos exemplos anteriores pode-se conhecer a dinâmica no atendimento bancário e também a dinâmica num hipermercado, foram citados vários fatores que influenciavam diretamente no desempenho do atendimento, o mesmo ocorre em redes de computadores.

Existem muitos fatores numa rede de computadores segundo Kurose (2006), que podem afetar em muito o desempenho, gerando lentidões, falhas, etc. De forma resumida citamos alguns fatores que podem afetar o desempenho da rede de computadores:

1. Disponibilidade
2. Tempo de Resposta
3. Utilização da Rede
4. Vazão
5. Confiabilidade
6. Eficiência
7. Relação Custo/Desempenho

Cada fator destes afeta diretamente as características da rede de dados e por extensão o desempenho da mesma  (TANENBAUM, 2003). Cada um desses parâmetros será abordado no nosso curso em seu devido capitulo apropriado.

### Técnicas para análise de desempenho

Na pratica três técnicas de avaliação de desempenho são as mais utilizadas, medição, modelagem analítica e simulação.

**Medição:** Tarefa que consiste na realização de medidas utilizando um sistema real ou protótipo. Normalmente é difícil comparar alternativas.  Para efetuarmos medições (como benchmarks, que veremos nas próximas aulas) devemos utilizar um instrumento de medição para coletarmos informações precisas, porém nem sempre um instrumento de medição é simples de se utilizar.

**Modelagem analítica:** Faz-se o uso de modelos matemáticos que correspondam ao sistema real. Esta técnica geralmente é aproximada e dependendo da forma como é construída pode gerar modelos bem próximos a realidade ou não, podendo algumas vezes ser limitada, mas na maioria dos casos eficiente. Em uma modelagem analítica, utilizamos a teoria das filas com itens como:

- **Processo de chegada.**
- **Processo de atendimento.**
- **Quantidade de servidores.**
- **Tamanho máximo da fila.**
- **Política de atendimento da fila.**

**Simulação:** Segundo Prado (2014), com o surgimento dos computadores a modelagem de filas, começa a fazer uso de modelos implementados em linguagens de programação. Simulação do comportamento de um sistema real. Em geral, utiliza-se em eventos discretos, com cada evento (chegada de usuário, término de serviço, etc.) sendo tratado no instante de sua ocorrência. É possível construir modelos mais próximos a realidade.

Segundo Almeida e Menascé (2002), todas essas técnicas são importantes quando estamos planejando a capacidade dos sistemas que atendem os serviços e aplicações na Web.

Prado (2014), cita muitos outros exemplos onde existem mais requisições do que recursos, gerando filas como: salão de cabeleireiro, bancos, supermercados, escritórios, transportes, etc.

Nota-se que a rede de dados é essencial para as comunicações modernas, as quais exigem cada vez mais desempenho, sendo assim, esse assunto é essencial para os profissionais de TI.