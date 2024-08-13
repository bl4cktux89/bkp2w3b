[![](https://ampli-images.s3.amazonaws.com/production/db293c5e-405a-42e3-aede-22c2897e95f3/original)](https://ampli-images.s3.amazonaws.com/production/db293c5e-405a-42e3-aede-22c2897e95f3/original)

Primeiramente, devemos observar atentamente o documento. O que pode ser um campo? Tudo aquilo que o usuário pode informar e ser armazenado no banco de dados. A lista de campos será:

- No de controle da ficha
- Data da nota
- Nome cliente
- RG cliente
- CPF cliente
- UF
- Cidade
- Código produto
- Descrição produto
- Quantidade
- Preço unitário
- Preço item
- Valor total da nota

E como podemos encontrar as tabelas? Uma dica é observar a lista de campos, por exemplo, os campos: Cod Produto e Descrição do Produto. Esses dois campos já indicam que existe a tabela Produto. O próprio documento, no caso a ficha de controle, também é uma tabela (geralmente o documento modelado acaba virando uma tabela). Podemos listar as seguintes tabelas:

- Ficha de controle
- Cliente
- Produto
- Cidade
- Estado

Lembre-se de que após o relacionamento entre as tabelas poderão aparecer as tabelas associativas.