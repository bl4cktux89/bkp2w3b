### Introdução

Quando desejamos atingir níveis elevados de qualidade de serviços em uma rede, é importantíssimo planejar sua capacidade para que as aplicações funcionem de forma eficiente. Os recursos a serem compartilhados em uma rede são finitos e geram custos altos para a empresa, por isso segundo Menascé (2002), devemos fazer o planejamento da capacidade da rede para trazer eficiência nas aplicações com baixo custo.

Levando em conta os serviços na web, para se conseguir níveis desejáveis de funcionalidade, devemos otimizar ao máximo o uso dos recursos de rede, determinando a demanda dos serviços e a capacidade dos recursos existentes.

### Planejamento de capacidade em redes

Em virtude do comprometimento com a qualidade dos serviços transportados e a limitação física dos recursos, como é o caso da capacidade da banda, as redes possuem um ponto flutuante de saturação dos recursos, com isso, a rede impede o ingresso de novos serviços ou começa a sofrer uma queda em seu desempenho por causa do congestionamento. O ponto de saturação é flutuante, pois depende de fatores externos à configuração dos recursos da rede. Nestes casos uma eficiente política de QoS (Quality of Service), deve ser aplicada na rede segundo Zeng, Lei e Chang (2007) para administrar o uso de recursos de rede para as diversas aplicações na web, que por fim irão afetar diretamente a experiência do usuário final, QoE (Quality of Experience).

Os principais fatores externos são:

- Quantidade de tráfego.
- Requisitos de desempenho.
- Topologia das conexões.

A combinação destes três fatores especifica a carga de serviço em que a rede é submetida. A carga de serviço distinta aplicada sobre determinada rede resulta em diferentes quantidades possíveis de atendimento do serviço, portanto, o projeto de uma rede deve considerar a carga de serviço fundamental para o dimensionamento dos recursos da rede conforme descreve Cavanaugh e Odom (2004) e a correta aplicação de regras de QoS. Devemos sempre identificar os fatores externos com o maior detalhamento possível para adequar a rede aos serviços previstos.

Outros fatores que influenciam na capacidade de atendimento da rede são internos, referentes à configuração da rede. Podemos citar os diferentes recursos que podem ser reunidos na configuração física da rede, como a capacidade dos enlaces. Devemos levar em conta os equipamentos e as configurações utilizadas nas redes. Outra parte dos fatores internos diz respeito à configuração lógica dos mecanismos adotados para o controle do tráfego.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/7/2/327201/21876.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/7/2/327201/21876.jpg)

Qualidade de serviço e experiência do usuário

### Definindo a capacidade adequada

Muitas empresas investem pesado para criar uma ambiente web e mais ainda na manutenção e na atualização deste ambiente. Na maioria dos casos, a capacidade geral dele é desconhecida, e o planejamento e a aquisição da capacidade são feitos sem uma metodologia definida (ALLSPAW, 2008). Muitos administradores não tem a noção exata do que seja planejamento de capacidade, sendo este o divisor de águas que determina o tempo de vida de sua infraestrutura. Vamos analisar o esquema a seguir, que mostra os três principais elementos usados para definir a capacidade adequada para uma infraestrutura de web.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363529/27944.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363529/27944.png)

Capacidade adequada para infraestrutura web

**Acordo de níveis de serviços (Service Level Agreement – SLA):** é um contrato entre duas partes que especifica performance e qualidade de um serviço e determina o que acontece quando as métricas não são atendidas. É o instrumento formal para cobrança/prestação de contas dos níveis de serviços contratados. Deve conter valores aceitáveis (para que sejam alcançados) de, por exemplo, tempo de resposta, disponibilidade e taxa de processamento. Vejamos alguns exemplos:

- Exemplo 1: O serviço de busca a produtos no site não pode exceder 2 segundos no tempo de resposta.
- Exemplo 2: O tempo de resposta para os pedidos de vendas de um servidor não pode exceder 4segundos.
- Exemplo 3: O website precisa estar disponível pelo menos 99,99% do tempo de serviço.

Os valores de SLA não são fixos dependem da cultura de cada organização, por exemplo, o que é aceitável para uma empresa, pode não ser aceitável para outra.

**Tecnologias e padrões especificados:** para definirmos a capacidade adequada, é necessário um conhecimento específico dos equipamentos que irão compor a infraestrutura da ambiente web, como os equipamentos de conectividade, os meios físicos corretos, servidores e sistemas operacionais que atendam às necessidades do ambiente.

**Restrições de custo:** um dos maiores problemas para a implementação de serviços na web são os custos. Na maioria das empresas, as verbas disponibilizadas para a implementação são fixas. Administradores devem se preocupar não somente com custos fixos iniciais, mas também com custos mensais.

1. Custos fixos: envolvem valores de aquisição de hardware e software, servidores, equipamentos de conectividade e meios físicos.
2. Custos mensais: envolvem os valores com serviços de telecomunicações com os links de dados, com pessoal especializado para manter o sistema em funcionamento e com treinamento periódico para a equipe.

### Metodologia de planejamento de capacidade

Vamos propor uma metodologia de planejamento web mais genérica, uma vez que os serviços de web requerem uma complexidade maior devido à heterogeneidade do ambiente, ou seja, em um mesmo ambiente podemos ter vários tipos de meios físicos, servidores, sistemas operacionais e tipos de serviços. O esquema a seguir traz uma metodologia aplicável em qualquer sistema de serviços web.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363538/28001.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363538/28001.png)

Conhecimento do ambiente

### Aplicação dos conceitos

Vejamos agora alguns exemplos práticos, aplicados ao estudo de carga de trabalho para o devido dimensionamento de velocidades de links.

### Exemplo 1

Uma empresa transportadora de cargas disponibiliza imagens digitalizadas de suas notas fiscais para seus clientes via intranet. São 100 clientes em que 80% estão ativos simultaneamente e realizam uma média de 100 transações por hora, com uma média de 5 imagens por transação. Cada imagem tem tamanho médio de 25.600 bytes. A empresa gostaria de saber se um link de 1Mbps atenderia essa demanda.

**Resolução:**

**1° Passo: Quantos clientes (Qc):   100 clientes em que 80% estão ativos simultaneamente.**

**2° Passo: Quantidades de transações (Qt): 100 transações por hora - vamos passar para segundos, pois a velocidades dos links e dada em bits por segundo, 1 hora equivale a 3600s.**

**3° Passo: Tamanho ou quantidade de arquivos em bits (Qa): 5 arquivos de imagem com tamanho médio de 25 600 bytes, lembrando que 1 byte é 8 bits**

**4° Passo: Equacionando todos os elementos : Link necessário (Ln): Ln = Qc*Qt*Qa**

**Link (Ln) = (100 x 0,80) x 100/3600 x (5 x 25.600 x 8)** **Link (Ln) = 80 X 0,0277 X 1024000**

**Link = 2269184, ou seja, será necessário aproximadamente 2,27Mbits por segundo (2,27Mbps).**

**Sendo assim um link de apenas 1Mbps, será insuficiente.**

### Exemplo 2

Um website de vendas de passagens online, está dimensionando a capacidade do link. Analisando seus logs de acesso, observou-se que a média diária era de 1.000.000 de operações HTTP por dia e o tamanho médio de cada foi de 10.000 bytes. Devemos calcular a banda necessária para esse link utilizando como base o cenário atual.

**Resolução:**

**Para a correta resolução, devemos montar o cálculo com base nos dados coletados no enunciado:**

**1° Passo: Calcular a quantidade de operações por dia (Od), ou seja, a média diária de 1.000.000 de operações HTTP, dividido pela quantidade de segundos de um dia, para sabermos a quantidade de transações por segundo.**

**2° Passo: Tamanho ou quantidade de arquivos em bits (Qa), ou seja, multiplicar o tamanho dos bytes transportados por oito para acharmos o valor em bits.**

**3° Passo:** **Equacionando todos os elementos:  Largura de banda (Lb) = Od * Qa**

**Largura de Banda (Lb) =[1.000.000 / (24x60x60)] x (10.000x8)**

**Largura de Banda (Lb) = (1000000 / 86400) X 80000**

**Largura de Banda = 925925, 93 bits por segundo, ou aproximadamente 926 Kbps.**

### Exemplo 3

Uma empresa deseja analisar o atendimento aos pedidos feitos em seu servidor web, este servidor possui apenas um processador. Foram coletados os dados das tabelas abaixo. O objetivo é saber se o servidor fica ocupado em um nível maior do que 80%, o que provocaria maior índice de manutenção. Neste caso, um novo processador será adicionado a esse servidor para a melhoria do atendimento dos pedidos, considerando uma jornada de trabalho de 8 horas por dia.

![[Screenshot_from_2022-03-29_21-33-57.png]]

**Resolução:**

**1° Passo: Cálculo da média da chegada dos pedidos no servidor:**

**Primeiramente devemos encontrar o total de frequência em dias, somando os valores da coluna de frequência em dias da tabela da esquerda.**

**Frequência = 1 + 3 + 5 + 9 + 10 + 11 + 9 + 7 + 3 + 2 + 1**

**Frequência = 61**

**Em seguida, devemos multiplicar linha a linha e somar os resultados, para sabermos o número total de pedidos e dividi-lo pela frequência, o resultado será a média de chegadas (Mc).**

**Mc = (8x1)+(9x3)+(10x5)+(11x9)+(12x10)+(13x11)+(14x9)+(15x7)+(16x3)+(17x2)+(18x1)/61**

**Mc= 778/61**

**Mc = 12,75**

**2° Passo: Cálculo da média de atendimentos (Ma) por dia:**

**O raciocínio é idêntico ao cálculo da média de chegadas.**

**Frequência = 2 + 4 + 6 + 6 + 9 + 11 + 10 + 7 + 3 + 2 + 1**

**Frequência =  61**

**Ma = (12x2)+(13x4)+(14x6)+(15x6)+(16x9)+(17x11)+(18x10)+(19x7)+(20x3)+(21x2)+(22x1)/61**

**Ma = 1018/61**

**Ma = 16,69**

**3° Passo: Calcular a porcentagem de utilização do serviço**

**% de utilização do serviço = Mc / Ma**

**% de utilização do serviço = 12,75 / 16,69**

**% de utilização do serviço = 76%**

**Com essa análise chegamos à conclusão de que o servidor atende à demanda, uma vez que a meta não ultrapassou os 80% permitidos.**