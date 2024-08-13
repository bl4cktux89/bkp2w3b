### Introdução

Quando pensamos em resolução de um problema usando os recursos  do computador , associamos a ideia de custo computacional, para um entendimento melhor, algumas noções sobre computação são essenciais, pois o custo computacional está associado diretamente aos conceitos de computabilidade,  complexidade e processamento, sendo assim, definimos estes conceitos abaixo:

- **Computabilidade** ? Está relacionado à existência de um algoritmo que resolva o problema, pois existe problemas que é impossível gerar um algoritmo para resolvê-lo.
- **Complexidade** ? Está relacionado à factibilidade da execução do algoritmo, abordaremos mais detalhadamente abaixo.
- **Processamento** ? Expressar o algoritmo em uma linguagem processável pelo computador e executar o programa no computador.

Um problema é computável se existe um procedimento que o resolva em um número finito de passos, ou seja, se é possível fornecer um algoritmo que leve à sua solução (ZUBEM, 2008).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/2/267292/15465.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/2/267292/15465.png)

Complexidade

### Complexidade Computacional

A teoria da complexidade computacional é um ramo da matemática que procura classificar os problemas computacionais de acordo com o seu grau de dificuldade, objetivando classificar os problemas que podem ser resolvidos por algoritmos computacionais de forma eficiente em diversas classes (OLIVEIRA, 2010). Essas classes são divididas de acordo com a quantidade de recursos computacionais necessários e suficientes para resolver cada problema.  Para medi-las podem ser abordadas duas instâncias: **espacial e temporal.**

Na **complexidade espacial** preocupa-se com a quantidade de recursos físicos. No caso _**hardware**_ do computador, como memória, disco e processador, esses recursos influenciam no desempenho da execução do algoritmo. Já na **complexidade temporal** preocupa-se com o tempo de execução.  Os pesquisadores reconhecem que nem todos os problemas podem ser resolvidos tão rapidamente,  são classificados como problemas computacionalmente difíceis de resolver (MITCHELL, 1997; TEIXEIRA, 1998).

### Problemas "P" e "NP"

Na teoria da complexidade computacional, os problemas são classificados de acordo com o tempo gasto pelo algoritmo para encontrar a solução, nesta classificação utilizam-se as letras P e NP para denotar classes de problemas computacionais. P significa “tempo determinístico polinomial” e NP “tempo não determinístico polinomial”. (OLIVEIRA, 2010; JIAN-MING, 2013; ERICKSON, 2009).

Os problemas P, são conjuntos de problemas com soluções que podem ser encontradas de forma eficiente e em tempo viável pois, podem ser resolvidos em tempo polinomial por algum algoritmo determinístico (SHPARLINSKI, 2003). Os problemas NP, são conjuntos que contém os problemas computacionais com soluções que podem ser verificadas de forma eficiente, mas não podem ser encontradas eficientemente. Significam e indicam problemas para os quais se utiliza algoritmos não determinísticos, ou seja, algoritmos que geram soluções factíveis cuja viabilidade pode ser verificada em tempo polinomial. Ainda dentro dos problemas NP, existem os chamados NP-hard, problemas NP muito difíceis de se resolver (SHPARLINSKI, 2003).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/9/269979/13028.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/9/269979/13028.jpg)

Redes complexas

Cobham e Edmonds (1965) entre outros (EISELT; SANDBLOM, 2004), sugerem que um algoritmo é eficiente quando a função do tempo de execução definida pelo número de passos de sua rotina é limitada por uma função algébrica, ou seja, por uma função polinomial.

Conforme a equação (1), um polinômio de grau 3 é composto pela soma de vários monômios, neste caso cada monômio representando o tempo de execução de determinados passos dentro do algoritmo, sendo assim, mesmo que as quantidades de passos aumentem, resultará no máximo um polinômio de grau maior, ou com maior quantidade de parcelas, resultando numa soma do tempo no final, conforme a equação (2).

![[Screenshot_from_2022-03-21_21-29-47.png]]

O tempo neste caso cresce sempre somando parcelas na função polinomial, mas nunca se multiplicando. Esta definição apresenta diversas propriedades interessantes, tem sido muito utilizada e tornou-se amplamente aceita afirmando que algoritmos polinomiais são computacionalmente viáveis.

Nos problemas classificados como NP, o tempo para resolução dos passos não cresce em tempo polinomial, mas sim, de forma exponencial. Cada novo passo multiplica o tempo da execução do algoritmo. Para problemas com muitos passos o tempo resultante pode ser muito alto, tornando a espera pelo processamento impraticável. Um exemplo de função não polinomial é mostrado na equação (3).

![[Screenshot_from_2022-03-21_21-30-16.png]]

Um exemplo comparativo do **custo computacional**  
 é mostrado na tabela abaixo, onde são avaliadas funções polinomiais e não polinomiais. Segundo as pesquisas de Devlin (2008), N representa o número de passos da rotina, em questão. Considera-se que os tempos são obtidos analisando um computador que consiga realizar um milhão de operações aritméticas básicas por segundo.  

![[Screenshot_from_2022-03-21_21-30-48.png]]

### Classificação de problemas segundo sua complexidade

1. **Indecidível:** são problemas tão difíceis, que nenhum algoritmo pode ser utilizado para resolvê-los. Há inúmeros problemas considerados desta classe, tais como o problema de decisão de Hilbert, o problema que envolve o teorema de Rice, o problema de parada da máquina de Turing, o problema da correspondência de Post, entre outros.
2. **Intratável:** problemas decidíveis, porém difíceis para os quais possivelmente não existe algoritmo que os resolvam em tempo polinomial. Entre os mais conhecidos estão os problemas de sequenciamento da produção, do caixeiro viajante, de partição em triângulos, de circuito hamiltoniano, de roteamento de arcos entre outros. Há abrangente literatura a respeito
3. **Tratável:** problemas para os quais existe algoritmo que os resolvam em tempo polinomial. Entre os mais conhecidos pode-se citar o problema dos circuitos eulerianos, o problema de cobertura de borda (_**edge cover**_), problema de gráficos com duas colorações, cardinalidade equivalente (_**cardinality matching**_), entre outros.