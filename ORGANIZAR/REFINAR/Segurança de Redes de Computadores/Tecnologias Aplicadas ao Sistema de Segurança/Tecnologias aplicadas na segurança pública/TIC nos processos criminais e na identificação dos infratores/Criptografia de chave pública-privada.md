[![](https://ampli-images.s3.amazonaws.com/production/dd47bc03-ce87-4c1c-b18d-5d84fb09a274/original)](https://ampli-images.s3.amazonaws.com/production/dd47bc03-ce87-4c1c-b18d-5d84fb09a274/original)

Buchman, Karatsiolis e Wiesmaier (2013) descrevem o processo de criação de chaves públicas da seguinte forma:

- uma pessoa ou organização cria, por meio de um _software_, um par de chaves: uma chave pública e uma chave privada;
- a chave pública poderá ser acessada por quem queira se comunicar seguramente com a pessoa ou organização que a gerou, e é disponibilizada, e será usada para cifrar a mensagem. Esta chave pública não tem utilidade nenhuma para decifrar a mensagem;
- a chave privada é secreta e fica sob custódia da pessoa ou organização que a gerou, e serve para decifrar a mensagem.

Quando alguém cria um par de chaves pública/privada é como se estivesse criando uma caixa segura (chave pública) que pode ser aberta apenas por uma única chave (secreta). Uma vez fechada, a caixa se tranca automaticamente, e quem está de posse não pode fazer mais nada.

Essa caixa é, então, reproduzida e distribuída para quem quiser mandar mensagens para quem a criou. A figura a seguir mostra este funcionamento:

[![](https://ampli-images.s3.amazonaws.com/production/69d829ac-3d55-4930-a79b-0c6bd4e90815/original)](https://ampli-images.s3.amazonaws.com/production/69d829ac-3d55-4930-a79b-0c6bd4e90815/original)

Mecanismo de criptografia de chave secreta (ou simétrica). Fonte: adaptada de Buchman, Karatsiolis e Wiesmaier (2013).

A chave privada de uma pessoa ou organização serve, ainda, para “assinar” a mensagem, e esta assinatura pode ser checada com a chave pública, que estará em poder do destinatário. O processo completo de uma comunicação entre Alice e Beto deve ocorrer assim:

- Alice gera um par de chaves privada e pública;
- Beto gera um par de chaves privada e pública;
- Alice envia sua chave pública a Beto;
- Beto envia sua chave pública a Alice;
- Alice cria uma mensagem cifrada com a chave pública de Beto;
- Alice usa sua chave secreta para “assinar” a mensagem;
- Alice envia a mensagem cifrada e assinada para Beto;
- Ao receber a mensagem, Beto usa a chave pública de Alice para checar se a assinatura é válida;
- Após checar a assinatura, Beto usa sua chave privada para decifrar a mensagem.

Para que esse mecanismo fique robusto, falta apenas resolver uma pequena vulnerabilidade: quem me garante que quando recebo uma chave pública da pessoa ou organização “X” foi realmente essa pessoa ou organização que gerou a tal chave? Em outras palavras, como é possível garantir a autenticidade da pessoa ou organização cuja chave pública tenho em mãos?

Surge aí a figura da entidade responsável pela autenticação. Esta entidade (uma pessoa ou uma organização confiável) recebe minha chave pública diretamente de minhas mãos, e quem quiser minha chave pública pode ir retirá-la com essa entidade. Essa entidade tem a responsabilidade de certificar as identidades das pessoas, e leva o nome de **Entidade Certificadora**.

No Brasil, os Correios, por exemplo, têm essa responsabilidade. Outras entidades também podem emitir esses certificados digitais, como no caso da Receita Federal.

Qualquer cidadão pode ter um certificado digital, que é usado para garantir sua identidade, além de garantir a segurança de suas mensagens. Toda essa infraestrutura leva o nome de ICP-Brasil, ou Infraestrutura de Chaves Públicas do Brasil.

Então, voltando aos laudos digitais, estes são emitidos e gerenciados usando este conceito. As polícias de vários Estados da Federação já adotam corriqueiramente este tipo de procedimento, por meio desta tecnologia.

Em São Paulo, por exemplo, a coleta de evidências periciais e os dados de processos investigativos são armazenados digitalmente, disponibilizados para a emissão de laudos, cuja emissão é garantida pela certificação digital administrada pela ICP-Brasil (SPTC-SP, 2015).

O processo de certificação digital utilizado na emissão e administração de laudos digitais traz várias vantagens aos processos em que são utilizados, atuando sobre dois dos principais elementos da segurança da informação e mais sobre um terceiro elemento, a autenticidade:

- confidencialidade – em casos de processos sigilosos, os laudos podem ser criptografados de maneira a estarem acessíveis apenas a quem de direito, impermeáveis a partes não autorizadas.
- integridade – os laudos são assinados digitalmente e qualquer alteração em seu conteúdo invalida a assinatura digital, o que é facilmente percebido pelo _software_ de certificação.
- autenticidade – os laudos podem ser utilizados em processos judiciais uma vez que podemos certificar sua procedência oficial.