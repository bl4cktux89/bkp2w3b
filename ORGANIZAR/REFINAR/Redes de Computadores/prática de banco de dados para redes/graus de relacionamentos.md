**Introdução**

O grau de um relacionamento refere-se ao número de entidades que participam de um relacionamento. Observe a seguir os diversos graus de relacionamentos:

**Relacionamento binário**

Um relacionamento binário é aquele envolve duas ocorrências de entidade.

Conforme observado na aula anterior, podemos classificar os relacionamentos binários em:

- **1:1 (um-para-um):** cada ocorrência de uma entidade relaciona-se com uma e somente uma ocorrência da outra entidade.
- **1:N (um-para-muitos):** uma ocorrência da entidade 1 relaciona-se com muitas ocorrências da entidade 2, mas cada ocorrência da entidade 2 somente pode estar relacionada com uma ocorrência da entidade 1.
- **N:N (muitos-para-muitos):** em ambos os sentidos encontramos um ou mais relacionamentos de um-para-muitos, isto é, uma ocorrência da entidade 1 relaciona-se com muitas ocorrências da entidade 2 e vice-versa.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121685/a05i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121685/a05i01_md80_100.jpg)

**Relacionamento ternário**

Denominamos ternários os relacionamentos entre três conjuntos de entidades. Relacionamentos com quatro ou mais conjuntos de entidades são chamados de     n-ários, porém, sua utilização não é recomendada em virtude de sua complexidade. Sugere-se que sejam "quebrados" em relacionamentos binários e/ou ternários.

No exemplo a seguir, queremos garantir que a seguinte situação seja representada de forma apropriada: o professor x ministra a disciplina y para a turma z. Esta condição deve ser representada por meio de um relacionamento ternário.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121684/a05i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121684/a05i02_md80_100.jpg)

Observe que, no exemplo apresentado, cada par de ocorrências (turma, disciplina) está associado a, no máximo, um professor.

Podem estar associadas muitas disciplinas a um par (turma, professor), ou, em outros termos, um professor pode ministrar a uma determinada turma várias disciplinas.

Podem estar associadas muitas turmas a um par (disciplina, professor), ou, em outros termos, um professor pode ministrar uma determinada disciplina a várias turmas.

**Autorrelacionamento**

Representa o relacionamento entre ocorrências de uma mesma entidade.

- **Autorrelacionamento 1:1**

O diagrama a seguir representa a seguinte situação: uma ocorrência de pessoa exerce o papel de marido e outra ocorrência de pessoa exerce o papel de esposa. Uma pessoa pode ter no máximo um cônjuge (marido ou esposa).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121686/a05i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121686/a05i03_md80_100.jpg)

- **Autorrelacionamento 1:N**

A seguir, temos representada a seguinte situação: uma ocorrência de funcionário exerce o papel de supervisor e outras ocorrências de funcionário exercem o papel de supervisionado. Um supervisor pode ter muitos supervisionados, mas cada supervisionado tem apenas um supervisor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121687/a05i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121687/a05i04_md80_100.jpg)

- **Autorrelacionamento N:N**

E, finalmente, temos representada a seguinte situação: algumas ocorrências de produto exercem o papel de composto e outras ocorrências exercem o papel de componente. Um produto pode entrar na composição de muitos outros produtos e cada produto é composto por vários (muitos) outros.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121688/a05i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121688/a05i05_md80_100.jpg)