[![](https://ampli-images.s3.amazonaws.com/production/22cbbd4e-a298-4664-a486-990055cfb392/original)](https://ampli-images.s3.amazonaws.com/production/22cbbd4e-a298-4664-a486-990055cfb392/original)

### **Qual é o foco da aula?**

Nesta aula finalizaremos as regras de normalização, que servem como apoio para verificar se há inconsistências na modelagem do banco de dados.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- Identificar a normalização é um processo que visa diminuir a redundância no banco de dados;
- Compreender a dependência funcional transitiva ocorre quando o valor de uma coluna é dependente de outra que não compõe a chave primária, dependendo indiretamente de outra chave primária;
- Interpretar que uma tabela somente estará na 4FN se não existir dependência multivalorada.

### Situação-problema

Olá, seja bem-vindo a nossa última aula teórica.

Nesta aula finalizaremos as regras de normalização, que servem como apoio para verificar se há inconsistências na modelagem do banco de dados. Com certeza após aplicar algumas vezes essas regras, você fará a modelagem de forma automática.

Retomaremos o contexto profissional em que você se encontra, concluindo seu trabalho nesta seção. Para relembrar, você foi contratado para criar um banco de dados para um time de futebol. O documento selecionado para servir como apoio para a criação do banco de dados é uma ficha de controle dos jogos realizados. Nas seções anteriores já realizamos, a partir do documento apresentado, o levantamento dos campos e aplicamos a Primeira Forma Normal  e a Segunda Forma Normal nas tabelas.

O banco de dados a ser elaborado para o time de futebol precisa estar muito bem modelado, e você não tem certeza se as tabelas criadas estão realmente  corretas. Como você pode garantir que seu trabalho foi realizado de maneira correta? Poderemos aplicar a Terceira Forma Normal e a Quarta Forma Normal nas tabelas encontradas? Será possível criar o Diagrama Entidade-Relacionamento a partir das tabelas normalizadas?

O primeiro passo é novamente observar o documento fornecido pelo time de futebol, na Figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/94478432-d6b1-4d00-86da-5d26a68f4708/original)](https://ampli-images.s3.amazonaws.com/production/94478432-d6b1-4d00-86da-5d26a68f4708/original)

Documento time de futebol. Fonte: elaborada pela autora.

Para realizar a modelagem do banco de dados para o cliente, você precisará aplicar todas as Quatro Formas Normais para conseguir garantir que as tabelas criadas a partir do documento estejam corretas. A partir das etapas que você já realizou nas seções anteriores, liste todas as tabelas na forma textual, separe cada Forma Normal e liste as tabelas criadas. Após, crie o Diagrama de EntidadeRelacionamento das tabelas e campos, utilizando uma ferramenta CASE de sua preferência, crie um dicionário de dados dos campos e finalize com um slide para apresentar ao seu cliente.