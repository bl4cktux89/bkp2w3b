[![](https://ampli-images.s3.amazonaws.com/production/a0603412-2a24-45dc-9846-e5dbdece0edb/original)](https://ampli-images.s3.amazonaws.com/production/a0603412-2a24-45dc-9846-e5dbdece0edb/original)

A Segunda Forma Normal, ou 2FN, deve obedecer a seguinte regra: uma tabela está na 2FN se, e somente se, estiver na 1FN e todas as suas colunas que não são chaves, dependam exclusivamente da chave primária (de toda a chave primária e não só de parte dela). Para estar na 2FN devemos aplicar as seguintes ações:

- Identificar as colunas que não são funcionalmente dependentes da chave primária da tabela.
- Remover o campo da tabela e criar uma nova tabela com esses dados.

Utilizando a tabela _Funcionário_, observe os seus campos: Funcionários **(****\#matrículaFunc**, nome, idade, valordahora, dtadmissão, Departamento, &idCidade). Para aplicar a 2FN, devemos criar uma tabela _Departamento_ e inserir a chave estrangeira na tabela _Funcionário_. As tabelas irão ficar da seguinte forma:

Departamento (**\#codDepart**, Departamento).

Funcionário (**\#matrículaFunc**, nome, dtNascimento, valordahora, dtadmissão, &codDepart, &idCidade).

No Quadro abaixo, observe a tabela Funcionário:

[![](https://ampli-images.s3.amazonaws.com/production/803dcc6e-8fb5-49ee-873d-96bbcf9f0550/original)](https://ampli-images.s3.amazonaws.com/production/803dcc6e-8fb5-49ee-873d-96bbcf9f0550/original)

Tabela Funcionário na 2FN. Fonte: elaborado pela autora.

A Figura abaixo mostra o Diagrama Entidade-Relacionamento resultante após aplicarmos a 1FN e a 2FN. Antes tínhamos somente uma única tabela, chamada Funcionário. Agora temos três tabelas.

[![](https://ampli-images.s3.amazonaws.com/production/bbae8549-2348-4214-8557-13ca0bc7b5d5/original)](https://ampli-images.s3.amazonaws.com/production/bbae8549-2348-4214-8557-13ca0bc7b5d5/original)

DER Funcionários na 1FN e na 2FN. Fonte: elaborada pela autora.

**➕ Pesquise mais**

Baixe o artigo que apresenta uma ferramenta de apoio ao processo de normalização de tabelas, visando contribuir principalmente com projetos _bottom-up_ de bancos de dados relacionais. Por meio da análise de dados, a ferramenta descobre dependências funcionais existentes que devem ser removidas.

ÁVILA, M. L. de; MELLO, R. S. [**Uma Ferramenta de Apoio à Normalização de Tabelas Relacionais Baseada na Análise de Dados**](https://www.researchgate.net/publication/255634082_Uma_Ferramenta_de_Apoio_a_Normalizacao_de_Tabelas_Relacionais_Baseada_na_Analise_de_Dados).

_______

Observe os campos apresentados sobre uma tabela de alunos: informações do aluno, endereço completo, telefones, notas. Como ficaria a tabela pelas informações passadas? Observe os campos na forma textual: aluno (informações, endereço, telefones, notas). Você como analista de sistemas ou programador não pode olhar  esses campos e achar que está tudo certo. Vamos analisar os campos dessa tabela:

- **Informações**: que informações são essas? Nome, data de nascimento?
- **Endereço**: é o endereço completo com o bairro, cidade e estado?
- **Telefones**: quantos números armazenar?
- **Notas**: quantas notas? A quantidade pode variar? Há um limite de notas?

Observe a quantidade de perguntas realizadas somente sobre  os campos da tabela aluno? E, é justamente essa a primeira tarefa de quem modela uma tabela: questionar o que puder sobre cada campo existente na tabela. A tabela _Aluno_ não está normalizada e pode ser vista na Figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/a034b110-e535-4d50-86be-b57c674cb821/original)](https://ampli-images.s3.amazonaws.com/production/a034b110-e535-4d50-86be-b57c674cb821/original)

Tabela Aluno não normalizada. Fonte: elaborada pela autora.

Vamos aplicar a Primeira Forma Normal na tabela Aluno. O primeiro passo é descobrir o que o campo Informações irá armazenar e nesse caso será: o CPF, RG, o nome, e-mail, foto e a data de nascimento. Aproveitando, podemos também criar uma chave primária para a tabela, como existe o CPF, iremos utilizar esse campo como chave primária. Agora a tabela ficará com novos campos, observe a Figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/9a8c82b4-f1fb-4a6f-9ff2-64133b35d7eb/original)](https://ampli-images.s3.amazonaws.com/production/9a8c82b4-f1fb-4a6f-9ff2-64133b35d7eb/original)

Tabela Aluno na 1FN – 1ª parte. Fonte: elaborada pela autora.

Resolvemos dois problemas na tabela: criamos a chave primária e “arrumamos” o campo informações e que agora são os campos: CPF, RG, nome, e-mail, data de nascimento e a foto do aluno. Um campo acabou virando outros seis campos. Terminou? Não! Será necessário verificar o campo endereço e saber: o que ele representa? O endereço deverá ter: rua, número, complemento, CEP, bairro, cidade e estado. Na Figura abaixo, verifique como ficará a tabela Aluno.

[![](https://ampli-images.s3.amazonaws.com/production/ee1f0f2f-46e0-4caa-99e8-095cc742ff4e/original)](https://ampli-images.s3.amazonaws.com/production/ee1f0f2f-46e0-4caa-99e8-095cc742ff4e/original)

Tabela Aluno na 1FN – 2a parte. Fonte: elaborada pela autora.

O problema do endereço na tabela Aluno foi resolvido, porém, sobraram os outros dois campos: notas e telefones. Quantas notas? Quantos telefones? Para a tabela Aluno vamos determinar 4 notas para serem cadastradas (para esses campos, sobre as notas, futuramente teremos que aplicar outras Formas Normais para resolver algumas dependências funcionais). E, para os telefones vamos classificar e guardar como: residencial, celular e do trabalho. A tabela Aluno ficará com os seguintes campos: Aluno (**\#CPF**, Nome, E-mail, RG, Foto, dtNascimento, Rua, Número, Complemento, CEP, Bairro, Cidade, Estado, Nota1, Nota2, Nota3, Nota4, Tefefone_Residencial, Telefone_Celular, Telefone_Trabalho).

_______

**🔁 Assimile**

Uma forma de deixar a sua tabela sempre na 1FN é sempre criar a chave primária e analisar o conteúdo que cada campo irá armazenar. Outra dica importante é sobre os campos: Cidade e Estado. Tanto Cidade quanto Estado sempre serão tabelas. Você nunca deverá deixar como um simples campo em uma tabela, caso faça isso o usuário poderá armazenar qualquer coisa como nome de cidade e de estado, gerando inconsistência nos dados armazenados.

_______

É possível aplicar a 2FN na tabela Aluno? Sim, porque existem campos que dependem da chave primária e que poderiam estar em outra tabela, são os seguintes campos: Cidade e Estado. Devemos tirar esses dois campos da tabela Aluno e criar duas novas tabelas: Cidade e Estado.

_______

**📝 Exemplificando**

Na Figura abaixo, você pode verificar o resultado final do exemplo de aplicação da 1FN e 2FN na tabela Aluno. Veja que em vez de termos uma tabela, já são três.

[![](https://ampli-images.s3.amazonaws.com/production/0f7fb5ab-d477-4c04-8478-05c14216fefe/original)](https://ampli-images.s3.amazonaws.com/production/0f7fb5ab-d477-4c04-8478-05c14216fefe/original)

DER Aluno na 2FN. Fonte: elaborada pela autora.

As duas primeiras formas normais que foram apresentadas, 1FN e a 2FN, já foram implicitamente implementadas no decorrer das aulas. Sempre que aplicamos o processo de modelagem de dados precisamos ficar atentos para inserir campos nas tabelas que realmente são dessa tabela. Não podemos “misturar” os campos das tabelas e essa é uma regra básica e essencial para a modelagem de dados.