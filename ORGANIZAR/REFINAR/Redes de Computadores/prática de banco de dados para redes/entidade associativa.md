A entidade associativa surge de um relacionamento de N para N, no qual existe uma associação dos atributos identificadores das duas entidades relacionadas, caracterizando uma nova entidade. A nova entidade gerada possui, normalmente, atributos próprios do relacionamento, isto é, ela só existe por causa do relacionamento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121770/a07i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121770/a07i01_md80_100.jpg)

Tomando-se como exemplo, novamente, uma clínica médica, observamos o seguinte:

- Um médico pode consultar N pacientes.
- Um paciente pode ser consultado por N médicos.
- Uma consulta é realizada em uma data e em um horário; possui um preço; pode ser paga por convênio ou pelo paciente; apresenta uma prescrição do médico e a relação de medicamentos. Esses são alguns atributos que pertencem apenas ao relacionamento CONSULTA.

Toda entidade possui um **atributo identificador** a partir do qual é feito o relacionamento das entidades. Ele é único e identifica cada ocorrência da entidade.

No diagrama a seguir, os atributos identificadores são: CRM e ID_Paciente.

No caso dos relacionamentos de N para N, não é possível transportar o atributo identificador de uma entidade para a outra que está relacionada, pois, assim, estariam sendo repetidos dados desnecessários.

Nesse caso, cria-se uma **terceira entidade**, chamada **consulta**, contendo os seguintes atributos: CRM, ID_Paciente, data e hora.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121769/a07i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121769/a07i02_md80_100.jpg)

No banco de dados, procura-se escrever o dado uma única vez e relacioná-lo com as demais entidades. Utilizando o exemplo da clínica médica, o nome de um médico deve ser apenas uma ocorrência na tabela de médico dentro do banco de dados. Embora a consulta tenha o médico responsável, não é necessário um atributo nome do médico, devemos substituí-lo por seu CRM, pois esse atributo o identifica dentro da entidade MEDICO. Do mesmo modo, o nome do paciente não precisa estar na entidade CONSULTA.

Transformamos um relacionamento de duas entidades de N para N acrescentando uma entidade e desmembrando o relacionamento.

Os atributos identificadores CRM e ID_PACIENTE são transportados para a nova entidade CONSULTA, acrescentando os outros atributos pertencentes à consulta.

Ao ligarmos as duas entidades, é possível notar que a cardinalidade deixa de ser de N para N.

Cada médico pode fazer N consultas, mas uma consulta é feita com apenas 1 médico.

Cada paciente pode fazer N consultas, mas cada consulta é feita com apenas 1 paciente.

A entidade CONSULTA é formada por identificadores de outras entidades, portanto, trata-se de uma entidade dependente, pois ela não existiria se não houvesse o relacionamento.

A entidade gerada por atributos identificadores de outras entidades também é chamada de **entidade fraca**.

A entidade fraca é identificada graficamente pelo retângulo de linha dupla, embora alguns autores prefiram utilizar a linha que liga a entidade ao relacionamento, em negrito. Observe os diagramas a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121772/a07i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121772/a07i03_md80_100.jpg)

**Ou**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121771/a07i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121771/a07i04_md80_100.jpg)