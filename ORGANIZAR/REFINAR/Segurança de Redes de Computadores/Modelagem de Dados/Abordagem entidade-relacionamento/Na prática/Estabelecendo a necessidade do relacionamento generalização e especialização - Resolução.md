[![](https://ampli-images.s3.amazonaws.com/production/8e52c6cc-eaef-4e18-9139-84705627898b/original)](https://ampli-images.s3.amazonaws.com/production/8e52c6cc-eaef-4e18-9139-84705627898b/original)

Fonte: Sorbis

Após fazer algumas pesquisas, o programador resolveu essa situação utilizando os conceitos de heranças no modelo lógico de banco de dados. A Figura abaixo mostra como ficaria a estrutura de generalização e especialização entre as entidades.

[![](https://ampli-images.s3.amazonaws.com/production/b33844c8-dd0b-45d0-82c0-96134d3e6aa9/original)](https://ampli-images.s3.amazonaws.com/production/b33844c8-dd0b-45d0-82c0-96134d3e6aa9/original)

Exemplo de generalização e especialização. Fonte: elaborada pela autora.

Na entidade Pessoa, podemos inserir o nome e o endereço, e as demais entidades poderão herdar esses atributos. Observe que a entidade Cliente foi generalizada para podermos classificar o Cliente entre Cliente Físico e Cliente Jurídico. Já a entidade Funcionário pode ser generalizada para que possamos criar a especialização Funcionário Horista e Funcionário Mensalista.