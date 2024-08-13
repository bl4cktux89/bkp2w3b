[![](https://ampli-images.s3.amazonaws.com/production/da1af510-7d1c-4359-bbd8-be168a8f34b8/original)](https://ampli-images.s3.amazonaws.com/production/da1af510-7d1c-4359-bbd8-be168a8f34b8/original)

Nas aulas anteriores foi realizada, primeiramente, a busca dos campos no documento e foram encontrados os seguintes: No de controle da ficha, Data da nota, Nome Cliente, RG Cliente, CPF Cliente, UF, Cidade, Código Produto, Descrição produto, Quantidade, Preço unitário, Preço item, Valor total da nota.

Após, foram encontradas as tabelas: Ficha de Controle, Cliente, Produto, Cidade, Estado.

Aplicamos a 1FN e a 2 FN nas tabelas encontradas.

**Para aplicar a 1FN devemos inserir a chave primária nas tabelas**:

Ficha (**\#numControle**, DtNota, valorTotal, Cidade, Estado)

Cliente (**\#CPF**, Nome, RG, Endereco)

Produto (**\#codProduto**, Descricao, precoUnitario, quantidade, precoTotal)

**Para aplicar a 2FN devemos criar as tabelas** Cidade e Estado e inserir as chaves estrangeiras na tabela Ficha.

Ficha (**\#numControle**, DtNota, valorTotal, &idCidade, &siglaEstado)

Cidade (**\#idCidade**, Cidade)

Estado (**\#siglaEstado**, Estado)

Para aplicar a 3FN devemos eliminar todos os campos dependentes, observando a tabela Produto, podemos retirar o campo precoTotal pois ele pode ser calculado a partir da quantidade do produto com o preço unitário do produto. Para aplicar a 4FN devemos verificar se não há campos multivalorados e não atômicos.

Nesse exemplo, temos o campo endereço que poderia ser inserido numa tabela, detalhando os campos que serão armazenados.

O DER resultante da modelagem do documento da Figura Documento time de futebol (da aula 3 desta unidade) pode ser analisado na Figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/c70b947e-72a2-4d56-aa98-8607a2f8ce3a/original)](https://ampli-images.s3.amazonaws.com/production/c70b947e-72a2-4d56-aa98-8607a2f8ce3a/original)

DER – Ficha de controle. Fonte: elaborada pela autora.

**➕ Saiba mais: Torne-se um Cientista de Dados**

Caro aluno, bem-vindo a mais uma trilha de capacitação! Ciência de dados está presente fortemente no mercado de trabalho. Aproveite este conteúdo para melhorar suas habilidades e ficar mais preparado para as oportunidades que surgirão! Sucesso!

[https://bit.ly/3C2bGZQ](https://bit.ly/3C2bGZQ)