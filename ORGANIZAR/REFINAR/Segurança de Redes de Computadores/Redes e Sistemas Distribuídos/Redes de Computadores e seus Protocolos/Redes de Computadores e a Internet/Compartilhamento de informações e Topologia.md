[![](https://ampli-images.s3.amazonaws.com/production/cd388a39-e404-4146-8954-6142229aa183/original)](https://ampli-images.s3.amazonaws.com/production/cd388a39-e404-4146-8954-6142229aa183/original)

Considerando o compartilhamento de informações, a referência é a forma como os dados são distribuídos pela rede, que pode ser classificada como:

**Cliente/servidor:** onde existem servidores provendo acessos, controle e dados a sistemas e clientes (estações de trabalho), que fazem uso de informações oferecidas pelos servidores.

Ponto a ponto: onde existe o compartilhamento direto entre dois hosts.

Além disso, há formas híbridas de compartilhamento de dados em uma rede, onde parte da comunicação é realizada ponto a ponto, porém controlada por servidores.

**Acesso**

Considerando a classificação por acesso a sistemas, as redes podem assumir abrangência interna, externa e global.

- **Intranet**: é uma rede privada e interna em uma organização, com acessos restritos a usuários e dispositivos homologados.
- **Extranet**: é uma rede que abrange sites corporativos com informações internas e acessos geograficamente externos. A internet como rede global de computadores é uma estrutura de extranet com acesso abrangente.

**Topologia**

Considerando a topologia, a classificação das redes refere-se à forma física em que os hosts de rede são interconectados, e a informação pode fluir de acordo com essa estrutura topológica, podendo ser: barramento, malha, estrela, anel, árvore e híbrida. A arquitetura híbrida faz a mescla de diferentes formas de topologias padrão.

1. **Topologia em malha**: apresenta uma ligação com links redundantes, em que cada host possui um link dedicado com os outros hosts. Trata-se de uma rede interessante, pois oferece melhores performances e segurança, mas quanto à implementação, é muito complexa e pouco utilizada. Nessa topologia, a vantagem é ter um link direto entre cada host, já a sua principal desvantagem é a complexidade das conexões. Exemplos podem ser vistos em interligações entre switches de rede, que são menos utilizados na atualidade.

A figura a seguir apresenta um modelo ilustrativo de topologia de rede em malha.

[![](https://ampli-images.s3.amazonaws.com/production/496274e1-5608-4d62-970d-8874a3ff337d/original)](https://ampli-images.s3.amazonaws.com/production/496274e1-5608-4d62-970d-8874a3ff337d/original)

Topologia de rede em malha. Fonte: elaborada pelo autor.

1. **Topologia em barramento**: trata-se de um modelo de ligação física de hosts em uma rede de computadores cujos dispositivos são ligados em um sistema multiponto, por meio de um cabo de rede que atua como link principal, chamado de backbone. Nessa topologia para redes locais, a vantagem econômica é a utilização de um único cabo para ligação dos hosts, porém essa ligação também é vista como desvantagem, uma vez que a interrupção desse cabo único representa a paralização total da rede. Esse modelo de conexão foi comum nos primeiros sistemas de redes de computadores, porém deixou de ser utilizado para redes locais.

Um exemplo em uso atual é a ligação de acesso para internet cabeada em residências, oferecida pela operadora de serviços de internet. A figura a seguir apresenta um modelo ilustrativo de topologia de rede em barramento.

[![](https://ampli-images.s3.amazonaws.com/production/5edb5f60-50cc-4bfc-85f0-ef18561754e7/original)](https://ampli-images.s3.amazonaws.com/production/5edb5f60-50cc-4bfc-85f0-ef18561754e7/original)

Topologia de rede em barramento. Fonte: elaborada pelo autor.

1. **Topologia em anel**: é um modelo em que cada dispositivo tem uma conexão direta e dedicada (ponto a ponto) com outros dois hosts, de forma que o conjunto de hosts forme um anel físico de hosts interconectados por enlaces de comunicação. Quando um host recebe um sinal destinado a outro, seu repetidor regenera os dados e encaminha-os para o destino.

Essa topologia foi implantada em redes conhecidas como _Token Ring_. Sua principal vantagem é a facilidade de instalação, já a desvantagem é que os dados são transmitidos em uma única direção. A figura abaixo apresenta um modelo ilustrativo de topologia de rede em anel.

[![](https://ampli-images.s3.amazonaws.com/production/009c48e2-a3e0-47ab-9ab5-a008c67194fa/original)](https://ampli-images.s3.amazonaws.com/production/009c48e2-a3e0-47ab-9ab5-a008c67194fa/original)

Topologia de rede em anel. Fonte: elaborada pelo autor.

1. **Topologia em árvore**: é uma topologia em hierarquia em que hosts estão organizados abaixo de dispositivos de rede, conforme ramificações de elementos, e utilizada, por exemplo, para ligação de dispositivos repetidores/gerenciadores de rede. A vantagem desse tipo de topologia é a organização da estrutura de dispositivos, o controle de hosts e o gerenciamento da rede. Como desvantagem, existe a necessidade de se prover sistemas redundantes para que a rede não seja prejudicada quanto a falhas em dispositivos. A figura a seguir apresenta um modelo ilustrativo de topologia de rede em árvore.

[![](https://ampli-images.s3.amazonaws.com/production/940dbca2-2c64-4728-903a-980292fb9b37/original)](https://ampli-images.s3.amazonaws.com/production/940dbca2-2c64-4728-903a-980292fb9b37/original)

Topologia de rede em árvore. Fonte: elaborada pelo autor.

1. **Topologia em estrela**: é uma topologia em que cada host tem um link direto (ponto a ponto) dedicado apenas com o concentrador/controlador de rede, que pode ser um hub, switch ou roteador. Os hosts são controlados pelos dispositivos concentradores, o que representa um modelo mais seguro de conexão e gestão de dados em rede. Essa topologia é amplamente utilizada em redes locais e sua vantagem principal é a centralização de conexões em um dispositivo de controle, que pode gerenciar todas as conexões. A desvantagem é dada quando há problema no dispositivo central, o que é tratado com redundância, juntamente a outros dispositivos, para que a rede não seja paralisada. A figura abaixo apresenta um modelo ilustrativo de topologia de rede em estrela.

[![](https://ampli-images.s3.amazonaws.com/production/3518365d-d6f0-4f81-af99-b96d2201a6a2/original)](https://ampli-images.s3.amazonaws.com/production/3518365d-d6f0-4f81-af99-b96d2201a6a2/original)

Topologia de rede em estrela. Fonte: elaborada pelo autor.