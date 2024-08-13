### Introdução

Os dados são armazenados de forma sequencial, como se estivessem “lado a lado”, não podendo guardar um dentro do outro, esse dado é armazenado inteiro, e junto com ele algumas informações como metadados(Informações sobre os dados, tais como nome do arquivo, data de criação, proprietário e tipo de arquivo), e um identificador único de objeto(geralmente um hash, que é um código criptográfico), e alguns outros metadados adicionais para facilitar a pesquisa. Utiliza-se uma abordagem de escalabilidade, tipo _**scale-out (**_ que significa ter mais de uma instância) permitindo que grandes volumes de dados sejam manuseados rapidamente  mantendo sua integridade. Assim na hora de resgatar um dado, ele busca por seu metadado, em object storage, onde os dados são divididos em duas partes, os dados do usuário e os metadados.

Um dos exemplos de Storage Object pode ser entendida como os ERPs (Enterprise Resource Planning) ou Planejamento dos Recursos da Empresa e os Data Warehouse, que fornecem informações, tais como relatórios de estoque, de produção e outros dados históricos das empresas, que podem auxiliar na tomada de decisão de um gestor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/9/2/9/2992931/43224.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/9/2/9/2992931/43224.png)

**BUSINESS INTELIGENCE E DATA WAREHOUSE**

**Data warehouse** é um depósito de dados que armazenam informações essenciais à tomada de decisão.

**Business Inteligence** é a inteligencia das informações que agregam valor ao negócio.

**Enterprise Resource Planning** é o planejamento de Recursos da organização.

**Vídeo**

Business Inteligence e Data Warehouse,

### OSD (Object Storage Device)

_**Object Storage Device**_ ou dispositivo de armazenamento de objetos, surgiu devido a rápida evolução das tecnologias de terceira plataforma, _**IOT, Big Data**_, entre outros, colaboraram para aumentar significantemente o volume de dados que um _**storage**_ precisa suportar, basicamente a terceira plataforma busca implementar computação em coisas que antes não usavam. Os armazenamentos por _**block**_ e arquivo oferecem certas limitações,  que o _**object storage**_ pode  solucionar. Um sistema baseado em object, quando feito corretamente não têm limite de expansão. Tornando essa tecnologia altamente rápida e escalável. Diferente do file storage, ele não é hierárquico, isso porque a maior parte dos dados da terceira plataforma não são estruturados, eis o porquê dessa arquitetura.

Os principais componentes de um armazenamento baseado em object são:

- **OSD Nodes:** Um ou mais nós OSD funcionam como controladores, eles são responsáveis pelo gerenciamento do armazenamento, eles fornecem recursos de armazenamento e computação. O serviço de metadados roda no servidor, armazenando e gerenciando os dados da rede. Para aumentar a sua capacidade basta adicionar outro nó a rede.
- **Rede interna:** É responsável por fazer a ligação entre o armazenamento e os nós OSD.
- **Armazenamento:** É o OSD propriamente dito, geralmente são usados discos mais baratos, de maneira que se for preciso aumentar a capacidade, mais discos são adicionados.

### Proteção de dados

A proteção de dados em object storage pode ser feita de duas maneiras, a primeira, é a replicação, que faz uma cópia exata do dado e a cópia é enviada para outro local, geralmente geograficamente afastado, e a segunda forma, seria a codificação de eliminação, que é uma técnica que segmenta um dado em partes menores e as codifica diminuindo seu tamanho, essas partes menores são enviadas para outros volumes, geralmente em outro lugar geograficamente, caso um pedaço da informação se perca, ainda é possível a recuperar com os outros pedaços matematicamente calculando a diferença entre as partes.

Resumidamente, podemos dizer que os principais conceitos do OSD são:

- a arquitetura scale-out(permite rápido crescimento),
- tecnologia multi-tenancy (Múltiplos inquilinos, ou seja, vários serviços ou aplicativos diferentes rodando no mesmo servidor de maneira isolada),
- políticas por metadados (facilita a administração de maneira global),
- global namespace (transforma todo o armazenamento em uma única área, fornecendo armazenamento de forma transparente), flexibilidade de acesso(pode ser acessado por API REST ou SOAP, para acesso web de maneira descentralizada),
- automatização(por meio das políticas podemos automatizar diversas coisas para facilitar nossas vidas),
- proteção de dados.

### Implementação

OSD pode ser implementado por software ou hardware. Por software é instalado diretamente no hardware, e não necessita hardware específico, diferente da implementação por hardware, que são sistemas que rodam em hardwares específicos, pré-configurados oferecendo maior desempenho e por um custo maior!

### Object Gateway

Um gateway de object storage age como um tradutor entre outros tipos de storage, ele pode aumentar a eficiência da rede de uma maneira geral, e também serve para por exemplo unir duas a infraestrutura de duas empresas em uma fusão.Suas interfaces são baseadas em file e/ou block e ele realiza a tradução.Entre outras funcionalidade o gateway object pode comprimir dados e evitar duplicidade, já que todos são validados por hashes únicas. Um gateway serve para realizar a comunicação com APIs(Interface de Programação de Aplicativos), a interface pode ser feito usando REST ou SOAP. E sua implementação pode ser física ou virtual.

### Resumo

O armazenamento unificado, é comum hoje em dia nos Data Centers, que tenhamos vários tipos de armazenamentos diferentes, file(NAS), block(SAN), object… Então o que fazer? Tenho que mudar todos para o mesmo tipo de storage? Qual a solução ideal? Simples, use todos! O armazenamento unificado têm uma controladora central que gerencia todos os outros storages, dessa maneira pode-se administrar mais facilmente toda infraestrutura de armazenamento como um todo, caso tenha que usar vários tipo de armazenamento essa é a opção mais recomendada.

Um exemplo de situação que isso poderia acontecer: Sua empresa tem um armazenamento em block de alta capacidade, com hardware específico, para rodar seu banco de dados, e posteriormente foi implementado um armazamento em file, por nivel de sistema, que pega relatórios internos dos funcionários no windows e para para o Linux usando o SAMBA, e para seus clientes, que são trilhões, você usa object storage, atribui meta tags em tudo, replica e faz backup, já que a primeira seria muito cara, e a segunda ineficiente, isso sem contar que pela quantidade apenas o object seria uma abordagem inteligente e rápida o suficiente. Ai vem a pergunta: "Como ligar tudo?", para isso se usa o armazenamento unificado.

Normalmente, já se tem uma infraestrutura preparada no local, o que torna inviavel o uso de apenas um dos casos, por isso se usa o estilo unificado, para aproveitar partes existentes, e apenas centralizar o controle de uma maneira centralizada, oque é mais facil de lidar do que ter três tipos de armazenamentos sem ligação. Isso sem contar que se perderia espaço util pelo fato de dividir o storage. Caso um dos dois atinja sua capacidade máxima, não será possivel usar o espaço vazio do outro.