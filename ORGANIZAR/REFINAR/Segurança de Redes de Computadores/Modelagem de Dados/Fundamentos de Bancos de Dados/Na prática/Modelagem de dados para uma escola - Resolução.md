[![](https://ampli-images.s3.amazonaws.com/production/1c39db9a-8db1-4746-8252-b0a20bacb416/original)](https://ampli-images.s3.amazonaws.com/production/1c39db9a-8db1-4746-8252-b0a20bacb416/original)

Para começar a resolver a situação problema, primeiramente precisamos apontar as entidades, que são: Aluno, Professor, Disciplina, Curso, Departamento e Horário. Observe que neste caso não faz sentido criar uma entidade chamada escola, visto que o banco de dados é para a própria escola. As entidades (tabelas) e seus campos (atributos) podem ficar da seguinte forma:

- **Aluno**: matrícula-aluno, nome, endereço, e-mail, telefone, dtnasc, foto, etc.
- **Professor**: número-identificação, nome, e-mail, fone, dt-nasc, dt-admissão, etc.
- **Curso**: sigla-curso e nome-curso.
- **Disciplina**: código-da-disciplina, nome e carga-horária.
- **Departamento**: código-do-departamento, nome e sigla.
- **Horário**: código-horário, horário, sala, sigla-curso e sigla-disciplina.

Observações importantes: note que na entidade Horário, apareceram dois campos que são de outras entidades. Isso ocorre devido ao relacionamento entre as entidades (na próxima unidade esse exemplo ficará mais claro). Outra situação são os nomes dos atributos: primeiro, eles não foram abreviados para que você possa compreender melhor (mas na realidade esses atributos ficam sempre abreviados) e, segundo, você poderá incluir novos atributos sem problemas.