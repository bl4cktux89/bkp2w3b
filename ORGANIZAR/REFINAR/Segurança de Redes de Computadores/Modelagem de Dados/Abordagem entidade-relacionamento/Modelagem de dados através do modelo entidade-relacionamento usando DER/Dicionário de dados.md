[![](https://ampli-images.s3.amazonaws.com/production/93cfb31f-d1c6-4e56-8a92-dfaacb48d500/original)](https://ampli-images.s3.amazonaws.com/production/93cfb31f-d1c6-4e56-8a92-dfaacb48d500/original)

Cada empresa de desenvolvimento de software possui o seu próprio padrão de dicionário de dados, porém, Korth, Silberschatz   e Sudarshan (2012) afirmam que um dicionário de dados deve ter várias informações, como as seguintes:

- Descrição dos nomes das tabelas, relações e atributos.
- Tipos dos dados (domínio) e seus respectivos tamanhos.
- Descrição detalhada das chaves utilizadas.
- Nomes dos usuários com suas permissões sobre a tabela.

O nível de detalhamento do dicionário de dados é opcional, mas ele acaba se tornando um documento fundamental, sendo muito requisitado quando o banco de dados apresenta problemas e precisa sofrer manutenção. É comum que a pessoa que realizará a manutenção não seja a mesma que criou o banco de dados, por isso a documentação dos campos é fundamental para acelerar o processo de manutenção. O Quadro abaixo mostra outra forma de dicionário de dados, mais robusta e com mais informações.

[![](https://ampli-images.s3.amazonaws.com/production/e7fe0149-5724-4343-a0fe-b22e26bd0e71/original)](https://ampli-images.s3.amazonaws.com/production/e7fe0149-5724-4343-a0fe-b22e26bd0e71/original)

Dicionário de dados da tabela funcionário modo completo. Fonte: elaborado pela autora.

**➕ Pesquise mais**

Saiba mais sobre o uso de _metadados_ como forma de padronização, sendo utilizados em bibliotecas digitais como ambiente propício para   a recuperação da informação.

CASTRO, F. F.; SANTOS, P. L. V. A. C. [Os metadados como instrumentos  tecnológicos  na  padronização   e   potencialização dos recursos informacionais no  âmbito das  bibliotecas digitais na era da web semântica](https://periodicos.ufpb.br/ojs/index.php/ies/article/view/840). Inf. & Soc.: Est., João Pessoa, v. 17, n. 2, p. 13-19, maio/ago. 2007.

_______

Para exemplificar um modelo lógico de entidade- relacionamento, vamos modelar um estudo de caso. Uma imobiliária especializada em aluguel de casas e apartamentos do litoral de Santa Catarina necessita de um software para ajudar no gerenciamento dos aluguéis e oferecer melhores ofertas para seus clientes. Após diversos contatos com a imobiliária, ficou estabelecido que os seguintes requisitos deveriam ser atendidos pelo banco de dados:

- Para cada imóvel deverá ter registrado: seu tipo (casa ou apartamento), quantidade de quartos e banheiros, se possui vista para o mar e preço da diária.
- As informações dos proprietários e dos inquilinos deverão ser armazenadas separadamente. Os proprietários podem ter vários imóveis que podem ser alugados para vários inquilinos.
- Além das informações sobre o munícipio ao qual o imóvel pertence, deverá também ser informado o nome da praia mais próxima a ele.
- Os imóveis são todos os itens que compõem a mobília, e os mais verificados são: cama, geladeira, freezer, televisor, ar-condicionado, entre outros. Neste caso, é importante que seja informada a quantidade de cada item.
- Deverá ser realizado e registrado um contrato exclusivo para os aluguéis com os inquilinos e os imóveis respectivamente alugados por eles.

Com os requisitos listados, podemos identificar primeiramente as entidades que se destacam: imóvel, tipo de imóvel, cidade, praia, proprietário, inquilino, contrato de aluguel e mobília.

Para expressar graficamente o diagrama de entidade- relacionamentos, utilizamos a notação “Pé de Galinha” de James Martin, de acordo com Coronel e Rob (2011). Para entender o diagrama da Figura abaixo, observe as entidades e seus atributos.

[![](https://ampli-images.s3.amazonaws.com/production/f1bc83a5-efba-4fd2-ae5f-b1eeae0d9818/original)](https://ampli-images.s3.amazonaws.com/production/f1bc83a5-efba-4fd2-ae5f-b1eeae0d9818/original)

DER - Imobiliária. Fonte: elaborado pela autora

Para melhor entendimento do diagrama da imobiliária, considere os seguintes itens:

- Observe as setas que ligam as tabelas, o lado que tem três pontas está representando o lado N, o que possui uma ponta é o lado 1.
- Observe que há as siglas PK e FK em alguns campos.
- PK significa _Primary Key_ ou a chave primária da tabela.
- FK significa _Foreign Key_ ou a chave estrangeira da tabela.

O dicionário de dados da tabela imóvel pode ser observado no Quadro abaixo. Para fins didáticos, estamos criando o dicionário de somente uma tabela e com poucos campos. Vale ressaltar que os acentos das palavras foram preservados, mas na criação do modelo físico no SGBD, os acentos deverão ser evitados.

[![](https://ampli-images.s3.amazonaws.com/production/e9b66345-689f-4498-af02-ec0c831f407f/original)](https://ampli-images.s3.amazonaws.com/production/e9b66345-689f-4498-af02-ec0c831f407f/original)

Dicionário de dados da tabela imóvel. Fonte: elaborado pela autora.

**💭 Reflita**

Na Figura acima é demonstrado o diagrama de entidade-relacionamentos como sendo uma solução inicial para a modelagem do banco de dados da imobiliária. Em um DER sempre podemos agregar mais tabelas, além das que aparecem explicitamente no enunciado. Uma situação que o cliente não levantou foi a questão do contrato que o proprietário deve ter em relação ao seu imóvel. O que você faria para criar um contrato para o proprietário? Outra situação é que a imobiliária pode expandir suas atividades para outros estados. Como você poderia criar uma relação entre cidade, estado e praias?

_______

Nesta aula você pôde conhecer mais alguns aspectos do processo de modelagem de dados, como as estratégias de modelagem _top-down_ e _bottom-down_ e a documentação do desenvolvimento de um diagrama de entidade-relacionamentos.

Em sua vida profissional você conhecerá e usará modelos diferentes, adaptados pelas empresas de acordo com suas necessidades de desenvolvimentos. A necessidade de apartação das novas tecnologias determinará o  seu  sucesso  profissional.  Na próxima aula, abordaremos os padrões de modelagem com UML, uma linguagem de modelagem unificada e muito utilizada na programação orientada a objetos.