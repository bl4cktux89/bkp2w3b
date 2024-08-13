Granularidade é a extensão à qual um sistema é dividido em partes pequenas, ou o sistema propriamente dito. Consiste na mensuração do tamanho, escala e nível de detalhes do sistema.

Quanto mais bem detalhado for o comportamento dos objetos que envolvem o sistema, mais fina será sua granularidade.

Atualmente, a granularidade tem recebido particular atenção devido à sua importância em SOA (Arquitetura Orientada a Serviços) por ser um fator decisivo na definição de uma abordagem por componentes do sistema que permite maior flexibilidade (Orientado a Reusabilidade) ou na padronização que permite maior produtividade (Orientado a Negócios).

Uma solução distribuída também pode fazer uso de paralelismo de execução para melhorar o desempenho da aplicação, implicando que um determinado problema pode ser parcialmente resolvido em diferentes máquinas do sistema simultaneamente.

Neste sentido, existem os seguintes níveis de paralelismo:

- **Paralelismo de Granularidade Fina** (fine-grained);
- **Paralelismo de Granularidade Grossa** (coarse-grained)

O Paralelismo de Granularidade Fina implica em mais flexibilidade, porque há mais, pequenos incrementos, pequenas unidades funcionais, enquanto que o Paralelismo de Granularidade Grossa possui grandes pedaços de capacidade funcional como em grandes processos computacionais onde há poucas interações e poucos dados.

Assim, serviços com pouco detalhamento têm uma estrutura grande e, portanto, uma granularidade grossa (_**coarse-grained**_) também chamada de baixa granularidade.

Os serviços com muito detalhamento são serviços de pequena estrutura e possuem uma granularidade fina (_**fine-grained**_) ou alta granularidade.

Máquinas paralelas utilizam o paralelismo em níveis diferentes: no nível de instruções, de dados ou de tarefas, o que leva a uma classificação conforme o nível no qual o hardware dará suporte ao paralelismo.

É possível afirmar que a Taxonomia de FLYNN (FLYNN, 1972), que se baseia em dois conceitos, os fluxos de instruções e os fluxos de dados, é uma das mais clássicas da área de Processamento de Alto Desempenho (HPC - High Performance Computing), embora não abranja de forma detalhada todos os tipos de arquiteturas existentes hoje em dia.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293449/18521.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293449/18521.png)

Taxonomia de FLYNN - Fluxos de Instrução e Fluxos de Dados.

Fonte: Internet

**Alguns dos termos da Taxonomia de FLYNN são usados até hoje para descrever o tipo de paralelismo encontrado em algumas arquiteturas:**

• **SISD** (Single Instruction, Single Data):

Não expressam nenhum paralelismo, classe que representa as arquiteturas que trabalham com um único fluxo de instruções e um único fluxo de dado, remete ao Modelo de John Von Neumann com execução sequencial. É normalmente encontrado nos computadores mais antigos e nos computadores pessoais que não são multicore.

• **SIMD** (Single Instruction, Multiple Data):

Máquinas paralelas que executam exatamente o mesmo fluxo de instruções (mesmo programa) em cada uma das suas unidades de execução paralela, considerando fluxos de dados distintos. Nessa arquitetura enquadram-se os computadores Vetoriais e matriciais.

- **MIMD** (Multiple Instruction, Multiple Data):

Máquinas paralelas que executam fluxos independentes e separados de instruções em suas unidades de processamento. Podem-se ter programas diferentes, independentes que processam entradas diferentes, múltiplos fluxos de dados. Hoje em dia é uma arquitetura muito utilizada, pois os mais modernos computadores são caracterizados por poderem aplicar múltiplas instruções sobre múltiplos fluxos de dados. Como exemplo, temos os supercomputadores, clusters, grids computacionais, computadores multiprocessados e os microcomputadores multicore.

Outro tipo de classificação existente é responsável pelo modelo de programação a ser empregado no desenvolvimento das aplicações, dividindo as máquinas segundo o compartilhamento de memória:

- **Multiprocessadores**:

Máquinas com memória compartilhada possibilitam o modelo de programação multithread.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293410/18522.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293410/18522.png)

Funcionamento da multithread em uma CPU com Multiprocessador.

Fonte: Pag. 47 - Fig. 3.3. do Livro Sistemas Distribuídos - Princípios e Paradigmas

- **Multicomputadores**:

Já nos Multicomputadores, utiliza-se uma técnica de paralelismo que une CPU’s fracamente acoplados, utilizando-se da troca de mensagens para execução de uma determinada tarefa.

São máquinas onde cada elemento de processamento possui a sua própria memória e exigem o modelo de programação através da troca de mensagens entre seus componentes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293451/18524.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293451/18524.png)

Modelo de uma Rede de Interconexão.

Fonte: Livro Sistemas Operacionais Modernos, 2ª Edição.