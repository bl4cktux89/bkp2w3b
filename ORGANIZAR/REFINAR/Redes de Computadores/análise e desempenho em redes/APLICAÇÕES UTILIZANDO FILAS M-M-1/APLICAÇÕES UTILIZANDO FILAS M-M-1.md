### **Introdução**

Como já conceituamos as filas, cabe agora entender como calcular a capacidade de um sistema utilizando fórmulas específicas para cada necessidade. Nesta aula iremos compreender a teoria de filas M/M/1.

Uma fila M/M/1 é o modelo mais simples dentre os existentes em teoria de filas, no entanto é um dos modelos mais estudados.  Neste modelo tanto as chegadas como o atendimento são markovianos, implicando numa distribuição de Poisson ou a exponencial negativa, e temos um único atendente. Neste modelo será considerado a capacidade e população do sistema infinitos e disciplina de atendimento FIFO.

Para um modelo de filas M/M/1 são válidas as seguintes definições:

- **? = Ritmo médio de chegadas;**
- **IC = Intervalo médio entre chegadas (por definição: IC = 1/?);**
- **TA = Tempo médio de atendimento ou de serviço;**
- **? = Ritmo médio de atendimento de cada atendente (por definição: TA = 1/?);**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/5/7/15709/i01_1735.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/5/7/15709/i01_1735.jpg)

Modelo de Fila M/M/1

### **Relações básicas para o modelo M/M/1**

### Equações referentes à quantidade de clientes

- Equação para o número médio de clientes na fila (NF):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347304/nf1.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347304/nf1.png)

- Equação para número médio de clientes no sistema (NS):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347306/ns.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347306/ns.png)

### Equações referentes à tempos

- Equação para tempo médio durante o qual o cliente fica no sistema (TF):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347307/tf.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347307/tf.png)

- Equação para o tempo médio durante o qual o cliente fica no sistema (TS):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347308/ts.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347308/ts.png)

### Equações referentes à probabilidades

- Equação para a probabilidade de haver n clientes no sistema - (P):
    
    n
    

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347309/pn.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347309/pn.png)

- Equação para a probabilidade de que o número de clientes no sistema seja superior a um valor "r" - P(n>r):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347310/pn_r.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347310/pn_r.png)

- Equação para a probabilidade de que o sistema esteja ocioso - P(n=0):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347311/pn_0.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347311/pn_0.png)

- Equação para a probabilidade de que o sistema esteja ocupado (também conhecido como "índice de congestionamento" ou "taxa de utilização") - P(n>0):
    - A taxa de utilização também podemos definir como a relação entre o ritmo médio de chegadas e o ritmo médio de atendimento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347312/pnmaior.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347312/pnmaior.png)

### Relacionamentos entre as equações:

- Equação para calcular o número médio de clientes na fila (NF) e tempo médio de espera em fila (TF):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347313/nf_tf.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347313/nf_tf.png)

- Equação para calcular o número médio de clientes no sistema (NS) e o tempo médio gasto por cliente no sistema (TS):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347314/ns_ts.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347314/ns_ts.png)

- Equação para calcular o tempo médio de espera em fila e o tempo médio gasto no sistema:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347315/tf_ts.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347315/tf_ts.png)

- Equação para calcular o número médio de clientes em fila e o número médio de clientes no sistema:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347316/nf_ns.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/3/347316/nf_ns.png)

### Aplicação M/M/1

Vamos ver na pratica uma aplicação do método M/M/1. Tomaremos como base o seguinte cenário de uma análise da equipe de apoio administrativo.Uma equipe de apoio processa os formulários de requisição de peças para a linha de produção.

O processamento não deve sofrer atrasos, caso contrário, a produção será afetada, sendo assim, decidiu-se analisar a equipe como um todo, e não seus membros individualmente, o que resulta em um sistema de fila única e um canal de atendimento; os "clientes" são os formulários de requisição; não há restrição quanto ao número de requisições, portanto a população é infinita; os formulários são processados por ordem de chegada do tipo (FIFO); as chegadas de pedidos e frequência de atendimento seguem as curvas de Poisson, ou exponenciais, neste caso, aplicaremos o sistema M/M/1.

### Primeira etapa: levantamento estatístico

Nesta etapa, faremos o levantamento estatístico do número de pedidos por dia (em 120 dias).Com base nos dados coletados, multiplicam-se os pedidos por dia pela frequência em dias. Somam-se os resultados e em seguida calcula-se a média.

![[Screenshot_from_2022-03-21_21-56-06.png]]

Cálculo da média:

**?** = 1802/120 = 15,02 , considera-se 15.

Depois de achar a média **?** , calcularemos os dados coletados dos atendimentos por dia. O procedimento é o mesmo: multiplicam-se os atendimentos por dia pela frequência em dias e somam-se os resultados. Em seguida, calculamos a média ?.

![[Screenshot_from_2022-03-21_21-56-51.png]]

Cálculo da média:

**?** = 2489/120 = 20,74 considera-se 21.

### Segunda etapa: cálculo dos índices de desempenho.

Como ambas as distribuições são do tipo Poisson, podemos aplicar as equações.

Taxa de utilização: ? = ? / ? = 15 / 21 = 0,714 (71% de utilização).

NS = ? / (? - ?) = 15 / (21-15) = 2,5 pedidos na seção, em média.

NF = NS- ? / ? = 2,5 - 0,714 = 1,78 pedidos em média esperando na fila.

Como NF= ?xTF temos que TF=NF/ ?

TF = 1,78/15 = 0,12 dias, ou 57,6 minutos em média de tempo de espera na fila (considerando que um dia de trabalho tem 8 horas ou 480 minutos).

Como NS = ?xTS temos que TS=NS/ ?

TS = 2,5/15 = 0,17 dias, ou 81,6 minutos de tempo total na seção.

### Mais exemplos para filas M/M/1

### Filas na confeitaria.

Numa pequena confeitaria, apenas um empregado atende os clientes aos domingos.O modelo de chegada de clientes nesse dia segue uma distribui de Poisson, com uma taxa média de chegada de 10 pessoas por hora. Os clientes são atendidos na disciplina FIFO. O tempo gasto para atender um cliente também segue uma distribuição de Poisson, com um tempo médio de atendimento de 4 minutos. Determine:

- Qual a probabilidade de uma pessoa chegar a confeitaria e não ter que esperar?
- Qual a taxa de ocupação da confeitaria (sistema)?
- Qual o número médio de pessoas na confeitaria (sistema)?
- Qual o número médio de pessoas na fila?
- Qual o número médio de pessoas sendo atendidas?
- Qual o tempo na fila?

**Solução: Pelos dados temos:**

λ = 10 chegadas por hora. Portanto IC = 1/ λ = 1/10 = 60min/10 = 6min

TA = 4 minutos. Portanto, μ = 1/TA = 1/4= 0,25 clientes por minuto ou 15 clientes por hora.

- Calcular a probabilidade do sistema estar ocioso: P(n=0) = (μ- λ)/ μ

P(n=0) = (15-10)/15 = 1/3=0,33.

- Taxa de ocupação ρ = λ/ μ = 10/15 = 2/3 = 0,66.
- NS= 10(15-10)= 2
- NF= 2-0,66=1,33.
- NA= NS-NF = 2 – 1,33 = 0,66
- TF=10/15(15-10)=0,133 hora ou 8 minutos

### Filas no banco.

As chegadas a um caixa de banco seguem a distribuição de Poisson, com um tempo médio entre chegadas de 10 min. Assume-se que a duração de um atendimento siga uma distribuição exponencial, com média de 3 min e temos apenas um atendente.

- Qual a probabilidade de uma pessoa chegar ao banco e não ter que esperar?
- Qual a taxa de ocupação (sistema)?
- Qual o número médio de pessoas no banco (sistema)?
- Qual o número médio de pessoas na fila?
- Qual o número médio de pessoas sendo atendidas?
- Qual o tempo na fila?

**Solução: Pelos dados temos:**

IC = 1/ λ = 10 mim;  λ = 60min/10min = 6 clientes/ hora.

TA = 3 minutos. Portanto, μ = 1/TA = 1/3= 0,33 clientes por minuto ou 20 clientes por hora.

- Calcular a probabilidade do sistema estar ocioso: P(n=0) = (μ- λ)/ μ

P(n=0) = (20-6)/20 = 14/20=0,7.

- Taxa de ocupação ρ = λ/ μ = 6/20 = 0,3
- NS= 6(20-6)= 0,43
- NF= 0,43-0,3= 0,13
- NA= NS-NF = 0,43 – 0,13 = 0,3
- TF=6/20(20-6)=0,02 hora ou 1,28 minutos