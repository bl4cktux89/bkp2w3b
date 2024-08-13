[![](https://ampli-images.s3.amazonaws.com/production/be8f73bd-0d61-4535-85fd-161b578cb90d/original)](https://ampli-images.s3.amazonaws.com/production/be8f73bd-0d61-4535-85fd-161b578cb90d/original)

Para aplicar a 1FN primeiro devemos inserir a chave primária nas tabelas:

Ficha (**\#numControle**, DtNota, valorTotal, Cidade, Estado)

Cliente (**\#CPF**, Nome, RG, Endereco)

Produto (**\#codProduto**, Descricao, precoUnitario, quantidade, precoTotal)

Para aplicar a 2FN primeiro devemos criar as tabelas: Cidade e Estado e inserir as chaves estrangeiras na tabela Ficha.

Ficha (**\#numControle**, DtNota, valorTotal, &idCidade, &siglaEstado) Cidade (\#idCidade, Cidade) Estado (\#siglaEstado, Estado)