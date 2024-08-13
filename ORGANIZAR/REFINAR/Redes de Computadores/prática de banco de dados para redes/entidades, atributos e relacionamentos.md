**Entidade**

Conjunto de objetos do mundo real dos quais queremos manter informações no banco de dados.

As entidades representam os agentes que interagem em um relacionamento. Podem representar pessoas, documentos (pedidos, notas fiscais etc.), objetos e resultado de ações. Observe os exemplos a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121622/a03i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121622/a03i01_md80_100.jpg)

**Atributo**

Representa um dado associado a cada ocorrência de uma entidade ou de um relacionamento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121623/a03i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121623/a03i02_md80_100.jpg)

**Relacionamento**

É o conjunto de associações entre entidades.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121625/a03i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121625/a03i03_md80_100.jpg)

Exemplo: clínica médica.

Suponha que você tenha sido convidado para fazer a modelagem de dados de um sistema para uma clínica médica.

Tomando como exemplo essa clínica, vamos começar a fazer a modelagem dos dados. Inicialmente, vamos identificar algumas entidades envolvidas e analisar seu relacionamento.

A atividade exercida na clínica envolve o médico consultar o paciente. Nessa ação encontramos duas entidades: **médico** e **paciente** e o relacionamento é o ato de consultar. Desenhando o diagrama temos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121624/a03i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121624/a03i04_md80_100.jpg)

Uma entidade possui um conjunto de atributos, cada atributo está associado a um tipo de dado, por exemplo, para que cada médico seja identificado, precisamos dos seguintes dados: CRM, nome, especialidade e telefone. Esses são os atributos da entidade MÉDICO.

Quando o paciente chega para sua primeira consulta, é necessário que ele informe seu CPF, nome, telefone e data de nascimento. Esses são os atributos da entidade PACIENTE. Vamos desenhar os atributos no diagrama:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121626/a03i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121626/a03i05_md80_100.jpg)

No banco de dados, a entidade representa uma **tabela** de dados. Desenhando as entidades em forma de tabela, teremos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121627/a03i06_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121627/a03i06_md80_100.jpg)

As tabelas são as representações das entidades, contendo os dados armazenados. Essa é uma visão lógica dos dados no banco de dados.

A modelagem de dados ainda não está pronta, precisamos agora identificar quais as outras entidades envolvidas e aquelas associadas aos relacionamentos que  aparecem durante a análise.