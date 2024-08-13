**Cardinalidade**

É o número (mínimo/máximo) de ocorrências de uma entidade associada a uma ocorrência de outra entidade por meio de um relacionamento.

**Cardinalidade mínima**

Indica o número mínimo de ocorrências de uma entidade associada à outra ocorrência da outra entidade relacionada. Pode ser representada por 0 (zero) quando a associação é opcional (não existe correspondente na outra entidade) ou 1 (um) quando a associação é obrigatória (pelo menos um correspondente na outra entidade).

**Cardinalidade máxima**

Indica o número máximo de ocorrências de uma entidade associada à outra ocorrência de outra entidade relacionada. É representado por 1 (um) ou N (várias ou muitas).

Exemplo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121648/a04i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121648/a04i01_md80_100.jpg)

No exemplo apresentado, vamos imaginar duas entidades, uma de homens e outra de mulheres, alguns homens são casados com mulheres da outra entidade e outros não. Da mesma forma, algumas mulheres são casadas, outras não.

Para identificar a cardinalidade, deve ser feita a pergunta de uma entidade para outra.

Um homem pode ser casado no mínimo com quantas mulheres da outra entidade? E no máximo (legalmente!)?

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121649/a04i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121649/a04i02_md80_100.jpg)

Uma mulher pode ser casada no mínimo com quantos homens da outra entidade? E no máximo (legalmente!)?

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121650/a04i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121650/a04i03_md80_100.jpg)

Quando usamos a cardinalidade mínima e máxima, devemos escrever da seguinte forma: **mínima**, **máxima**.

Observe agora outro exemplo:

Uma empresa possui funcionários e seus dependentes; nem todo funcionário possui dependentes, mas todos os dependentes têm algum funcionário associado. Vamos colocar a cardinalidade analisando primeiro a entidade **funcionário**.

Um funcionário possui no mínimo **0** (nenhum) dependente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121652/a04i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121652/a04i04_md80_100.jpg)

Um funcionário possui no máximo **N** (vários) dependentes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121651/a04i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121651/a04i05_md80_100.jpg)

Agora, analisando a entidade **dependente**:

Um dependente tem no mínimo **1** (um) funcionário associado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121653/a04i06_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121653/a04i06_md80_100.jpg)

Um dependente tem no máximo **1** (um) funcionário associado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121655/a04i07_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121655/a04i07_md80_100.jpg)

Veja o INFOGRÁFICO com explicação passo a passo de como interpretar as cardinalidades em um DER (Diagrama Entidade Relacionamento).

[**INFOGRÁFICO**](https://ead.uninove.br/ead/disciplinas/web/_g/md80_100/a04if01_md80_100.htm)

**Grau de cardinalidade**

Grau de cardinalidade refere-se à cardinalidade máxima, observando-se ambos os sentidos. Portanto, podemos encontrar os seguintes graus de cardinalidade:

**1:1 (um para um)**

Uma ocorrência da **entidade 1** se relaciona no máximo com apenas **uma** ocorrência da **entidade 2** e uma ocorrência da **entidade 2** se relaciona no máximo com apenas **uma** ocorrência da **entidade 1**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121654/a04i08_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121654/a04i08_md80_100.jpg)

**1:N (um para muitos)**

Uma ocorrência da entidade 1 se relaciona com muitas ocorrências da entidade 2 e uma ocorrência da entidade 2 se relaciona com apenas uma ocorrência da entidade 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121657/a04i09_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121657/a04i09_md80_100.jpg)

**N:N (muitos para muitos)**

Uma ocorrência da **entidade 1** se relaciona com **muitas** ocorrências da **entidade 2** e uma ocorrência da **entidade 2** se relaciona com **muitas** ocorrências da     **entidade 1**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121656/a04i10_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121656/a04i10_md80_100.jpg)