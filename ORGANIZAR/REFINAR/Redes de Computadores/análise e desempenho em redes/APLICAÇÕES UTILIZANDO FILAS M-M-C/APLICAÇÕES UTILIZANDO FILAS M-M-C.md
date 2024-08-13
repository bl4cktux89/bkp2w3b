### Introdução

Dando continuidade ao modelo estudado anteriormente M/M/1, o modelo M/M/c apresenta tanto a chegada quanto o atendimento distribuições markovianos, mas com múltiplos servidores (PRADO, 2014).

Para um sistema M/M/c, são válidas as seguintes definições:

- ? = Ritmo médio de chegadas;
- IC = Intervalo médio entre chegadas (por definição: IC = 1/?);
- TA = Tempo médio de atendimento ou de serviço;
- ? = Ritmo médio de atendimento de cada atendente (por definição: TA = 1/?);
- c = quantidade de atendentes;
- Taxa de utilização ou de ocupação ? = ?/ c?

As fórmulas para o modelo M/M/c são muito complexas, sendo assim será utilizado para o devidos cálculos de P(n=0), quando o sistema está ocioso (livre) a consulta da tabela1.

Relações que serão utilizadas para o modelo M/M/c:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/7/354742/nf_mmc.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/7/354742/nf_mmc.png)

As relações abaixo continuam válidas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/7/354740/nf_tf.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/7/354740/nf_tf.png)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/7/354741/ns_ts.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/7/354741/ns_ts.png)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/9/6/7/196771/Untitled-1.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/9/6/7/196771/Untitled-1.jpg)

Modelo de Fila M/M/c

### Exemplo 1

Caetano é um dos críticos do funcionamento do serviço uma clínica veterinária, pois sempre que chama um veterinário ele nunca vem no mesmo dia.

Atualmente há dois veterinários, cada um atendendo em média 5 chamadas. Quanto aos pedidos de apoio a animais doentes verifica-se que chegam aleatoriamente, seguindo um processo de Poisson, a razão de 9 por dia. A direção resolveu discutir o caso, admitindo até mesmo contratar um novo veterinário.

Avalie a situação, contribuindo com informação que possa ser útil para uma tomada de decisão sobre a contratação. Considerado a fila tipo M/M/2.

**Resolução:**

**Ritmo de chegada --   ? = 9 chamadas/dia**

**Ritmo de atendimento ? ? = 5 chamadas/dia**

**Taxa de utilização --  ? = ?/ c*? = 9/2*5 = 0,9**

**Consultando a tabela 1  achamos o valor de P(n=0), no cruzamento da linha ? / ?  com a coluna número de servidores.**

**Para ? / ? = 1,8 e S = 2,  temos exatamente o valor de P(n=0) = 0,0526, não tendo necessidade de fazer o cálculo de interpolação.**

Objeto do estudo: pretende-se verificar se o a afirmação que o veterinário nunca vem no mesmo dia, é verdadeira ou não.

Número médio de chamados na fila.

**NF= 0,0526*(1,8)****2*****0,9/2! (1 ? 0,9)****2****=0,1540/0,02 = 7,7 chamadas.**

Finalmente, o tempo médio de espera na fila:

**TF = NF/ ? = 7,7/9 = 0,855 dias.**

Logo a afirmação de Caetano é indevida, visto as chamadas esperarem menos de um dia o atendimento.

![[29835.pdf]]

### Exemplo 2

Loja de fotocópias.

Uma loja de fotocópias duma empresa, fica aberta 40 horas por semana, dispõe de 2 fotocopiadoras. Os clientes chegam a razão de 33/hora e o tempo médio de serviço é de 3 minutos. Considerando o modelo M/M/2, determine:

1. O número médio de pessoas aguardando para a utilização da máquina.
2. O tempo médio que um cliente fica esperando
3. O tempo médio que um cliente fica na loja.

**Resolução:**

Ritmo de chegada --   λ = 33 clientes/hora

TA = 3 minutos/cliente. Portanto, μ = 1/TA = 1/3= 0,33 clientes por minuto ou 20 clientes por hora.

Ritmo de atendimento – μ = 20 clientes/hora

Taxa de utilização --  ρ = λ/ c*μ =  33/2*20 = 0,825

**Consultando a tabela 1  achamos o valor de P(n=0), no cruzamento da linha λ / μ  com a coluna número de servidores.**

**Para λ / μ = 1,60 e S = 2,  temos 0,1111 e para λ / μ = 1,80 e S = 2  temos o valor  0,0526, sendo assim há necessidade dp cálculo de interpolação para achar o valor 1,65.**

Calculando a interpolação de 1,65:

Na tabela a coluna **λ / μ** salta 0,2 em 0,2.

Temos que 1,65 pode ser decomposto na forma 1,60 + 0,5, sendo assim o excesso é 0,5, na coluna  **λ / μ.**

**Calculemos o valor de interpolação para esta coluna:** **(1,8 -1,6) / 0,5 = 4**

**Sendo assim o valor de interpolação da coluna S=2, será : 0,1111 - (0,1111 - 0,0526) / 4 = 0,1111 - 0,0146 = 0,0965. Portanto** **P(n=0) = 0,0965.**

1. **Número médio de pessoas aguardando para a utilização da máquina.**

NF= 0,0965*(1,65)2*0,825/2! (1 – 0,825)2= 3,54 clientes.

1. **Tempo médio que um cliente fica esperando.**

TF = NF/ λ = 3,54/33 = 0,11 horas = 6,4 minutos.

1. **Tempo médio que um cliente fica na loja.**

TS = NF + 1/ μ = 0,11 + 0,5 = 0,16 horas = 9.4 minutos.