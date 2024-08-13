# **Introdução da Unidade**

[![](https://ampli-images.s3.amazonaws.com/production/e00e54b8-76be-4335-8cd2-7c3850744042/original)](https://ampli-images.s3.amazonaws.com/production/e00e54b8-76be-4335-8cd2-7c3850744042/original)

### **Objetivos da Unidade**

Ao longo desta Unidade, você irá:

- esclarecer a importância do HTML;
- descrever o desenvolvimento do HTML5;
- aplicar formulários e tabelas em HTML.

### **Introdução da Unidade**

Ao longo dos anos, a internet tornou-se fundamental para a sociedade. Estamos sempre conectados à grande rede mundial de computadores e isso tem trazido mudanças profundas no mercado de trabalho; empresas que não estão na web correm o risco de deixarem de existir. Por esse motivo e outros, cada vez mais profissionais capacitados estão sendo requisitados na área de desenvolvimento web.

As aplicações web, ou seja, aquelas que são executadas a partir da internet, podem ser construídas usando-se uma gama de linguagens de marcação, estilo e programação. Portanto, o caminho para se tornar um desenvolvedor web é longo e envolve muita dedicação, e nesta unidade, você dará o primeiro passo.

Na primeira aula, você aprenderá os fundamentos da linguagem de marcação de hipertexto (HTML), suas versões, diferenças e elementos básicos.

Na segunda aula, você aprenderá sobre elementos estruturais da linguagem HTML e as _tags_ relacionadas à inserção de texto, listas, _links_ e imagens; conhecerá, ainda, o conceito de _iframes_ e de _design_ responsivo.

Por fim, na terceira aula, você aprenderá a construir tabelas e formulários, bem como conhecerá os tipos de campos de entrada e outros elementos.

Vamos lá?

# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/79f1ae29-1869-4dca-81b4-60de42b2bbd5/original)](https://ampli-images.s3.amazonaws.com/production/79f1ae29-1869-4dca-81b4-60de42b2bbd5/original)

### **Qual é o foco da aula?**

Nesta aula, você irá conhecer o desenvolvimento de sites.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- apontar problemas em códigos-fonte ;
- explicar a construção de novas páginas web;
- aplicar a linguagem HTML.

**Situação-problema**

Nesta aula, você aprenderá os fundamentos do desenvolvimento de websites; conhecerá, ainda, os serviços de hospedagem de páginas web e como são editados a partir de editores de códigos.

Aprender os fundamentos para construção de websites é fundamental para o sucesso no mercado de trabalho, que, a cada dia, requer mais profissionais da tecnologia da informação capacitados para lidar com aplicações web.

> Uma das linguagens fundamentais para o desenvolvimento web é a linguagem HTML, ou linguagem de marcação de hipertexto, que é a principal linguagem utilizada para construção de documentos web. Conhecer a fundo os elementos básicos do HTML é fundamental para se compreender, na prática, os princípios do desenvolvimento de aplicações web.

A fim de colocar em prática os conhecimentos a serem adquiridos nesta aula, imagine que você acaba de ser contratado como estagiário em uma empresa que vende planos de internet. A empresa que o contratou é bastante conceituada no mercado, entretanto, a maior parte das operações de vendas é realizada com métodos antigos, como ligações telefônicas. No começo das atividades dessa empresa, isso não era um problema, pois a maioria dos clientes não possuía acesso à internet, logo, requisitavam os serviços da empresa. Entretanto, nos últimos tempos, a empresa passou a focar na atração de clientes de outras provedoras de internet, tornando-se necessário construir aplicações web para isso.

Entre as funções que você deverá desempenhar, podemos listar: detecção de problemas em códigos-fonte da empresa e construção de novas páginas web.

Você, então, inicia o desenvolvimento de uma página web construindo o código HTML:

[![](https://ampli-images.s3.amazonaws.com/production/b80137a3-2dc2-4a61-a2b1-bb73a3e7a960/original)](https://ampli-images.s3.amazonaws.com/production/b80137a3-2dc2-4a61-a2b1-bb73a3e7a960/original)

Página HTML para comercializar planos de internet. Fonte: Elaborado pelo autor.

Em seguida, você testa essa página em um navegador do Google Chrome e obtém este resultado:

[![](https://ampli-images.s3.amazonaws.com/production/9568c48e-f46b-4b03-a9b3-8c2c91098c8a/original)](https://ampli-images.s3.amazonaws.com/production/9568c48e-f46b-4b03-a9b3-8c2c91098c8a/original)

Visualização no Google Chrome. Fonte: Captura de tela do Google Chrome elaborada pelo autor.

Entretanto, ao testá-la em outro navegador, você se depara com o seguinte problema:

[![](https://ampli-images.s3.amazonaws.com/production/ac20de25-210f-4355-b568-84ce570dfe82/original)](https://ampli-images.s3.amazonaws.com/production/ac20de25-210f-4355-b568-84ce570dfe82/original)

Visualização no Internet Explorer. Fonte: Captura de tela do Internet Explorer elaborada pelo autor.

Como resolver esse problema?

# **Conceito-Chave**

[![](https://ampli-images.s3.amazonaws.com/production/4f28ba77-7051-40b8-b801-7ff95360cc04/original)](https://ampli-images.s3.amazonaws.com/production/4f28ba77-7051-40b8-b801-7ff95360cc04/original)

Os primeiros computadores, ainda nos primórdios do século XX, eram estrondosas máquinas que ocupavam prédios inteiros, mas tinham um baixo poder de processamento. Naquela época, eles eram usados, principalmente, nos grandes centros de pesquisa e em bases militares para cálculos balísticos. Era o auge da Guerra Fria e os militares precisavam de meios rápidos para a troca de informações entre bases militares; surgiu, assim, a _ARPANET_, uma rede remota que interligava bases militares e permitia a troca de informações entre computadores (LAMBERT et al., 2005).

Mais tarde, as grandes universidades americanas obtiveram permissão para acessar a rede de computadores, que foi dividida em duas: (i) _MILNET_, rede de acesso exclusivo militar, e (ii) internet, rede disponível publicamente (LAMBERT et al., 2005).

Com a evolução dos componentes eletrônicos, surgiu a possibilidade de comunicação entre usuários comuns. Naquele tempo, vários protocolos foram implementados, como o protocolo TCP/IP, que passou a permitir que dispositivos construídos por diferentes fabricantes pudessem se conectar em uma linguagem universal. Entretanto, somente nos anos 1990 a web se popularizou devido ao surgimento de um novo protocolo de comunicação por meio de hipertextos, chamado HTTP (_Hypertext Transfer Protocol_) (GOURLEY et al., 2002).

______

🔁 **Assimile**

O hipertexto é um tipo de documento que vai além de blocos de textos comuns, agregando diversos outros componentes, como imagens, cores, sons, vídeos, entre outros. As páginas de hipertexto podem ser interligadas a partir das chamadas hiperligações, que são _links_ que permitem que o usuário acesse determinado documento com um único clique. Os _links_ se diferem de textos simples por serem exibidos em uma cor distinta, em geral, azul, além de serem sublinhados.

______

O protocolo HTTP foi criado por Tim Berners-Lee, professor do _Massachusetts Institute of Technolog_y (MIT) e fundador do W3C (_World Wide Web Consortium)_. O protocolo HTTP permitiu o surgimento de uma nova forma de acessar conteúdo em formato de hipertexto na chamada _World Wide Web_ (WWW) ou rede mundial de computadores. Por meio de navegadores de internet, um usuário conseguia acessar páginas web armazenadas em computadores remotos.

Entretanto, por muitos anos, a internet ficou restrita a um público que tinha maiores recursos financeiros, uma vez que computadores e até mesmo o acesso a linhas telefônicas (necessárias para conexões com a internet) tinham alto custo. A popularização da internet teve início nos anos 2000 com a melhoria da infraestrutura de comunicação e componentes eletrônicos.

Nos últimos anos, houve um crescimento significativo na quantidade e variedade de dispositivos eletrônicos conectados à internet, como _laptops, smartphones, tablets_, relógios inteligentes e os tradicionais computadores de torres, conectados por redes de comunicação disponíveis 24 horas. Além disso, devido ao fato de estarmos tão conectados, grande parte das aplicações, de banco de dados e servidores migraram para a “nuvem”, isto é, super computadores que armazenam informações, fornecem serviços e podem ser localizados em qualquer ponto geográfico.

[![](https://ampli-images.s3.amazonaws.com/production/b595eca4-04ba-499c-be32-d6b5bcf7eff4/original)](https://ampli-images.s3.amazonaws.com/production/b595eca4-04ba-499c-be32-d6b5bcf7eff4/original)

A internet é formada por uma grande rede de dispositivos conectados remotamente que engloba todo o mundo. Fonte: Shutterstock.

Além disso, faz-se importante destacar que, com o advento da internet, a quantidade de dispositivos e de aplicações _online_ também contribuiu para o aumento da quantidade de dados e informações enviadas para a nuvem para, em seguida, serem analisadas e auxiliarem na tomada de decisão das empresas, demandando uma maior utilização da internet.

Com a internet, os usuários puderam compartilhar informações por meio de locais específicos, chamados de páginas da internet, documentos web, websites ou apenas sites. As páginas da internet podem ser acessadas por meio de dois componentes básicos:

- um navegador de internet, também conhecido como _browser_ (Figura 1.4). São exemplos de navegadores: _Chrome, Firefox, Opera, Edge_ e _Safari_.
- um endereço URL (_uniform resource locator_ ou, na tradução, “localizador uniforme de recursos”).

[![](https://ampli-images.s3.amazonaws.com/production/e9da4d8d-cddd-4e34-a324-e6a75362ed07/original)](https://ampli-images.s3.amazonaws.com/production/e9da4d8d-cddd-4e34-a324-e6a75362ed07/original)

Estrutura de um navegador (browser). Fonte: Shutterstock.

_Browser_ é um programa de computador que recebe um endereço de URL, realiza uma requisição a um servidor remoto (também pode ser usado para visualizar arquivos locais), obtém os arquivos codificados em uma linguagem de marcação, interpreta-os e formata o documento que será exibido para o usuário. Em geral, navegadores são utilizados para acessar documentos de hipertexto (e veremos mais sobre isso na próxima aula).

______

**📝 Exemplificando**

As URLs não estão presentes apenas em navegadores; elas podem ser usadas como sistemas de navegação em redes para acesso de recursos e dispositivos. Observe, a seguir, uma ilustração de como funciona uma URL: protocolo://domínio:porta/caminho/recurso?busca\#identificador

- o **protocolo** indica o método de acesso, como HTTP (protocolo de transferência de hipertexto), HTTPS (transferência criptografada de hipertexto), FTP (protocolo de transferência de arquivos) e outros.
- o **domínio** indica o endereço em que se encontra o recurso.
- a **porta** filtra o acesso a um dispositivo alvo. Por exemplo: o protocolo HTTP usa a porta 80 e o HTTPS a 443.
- o **caminho** indica a localização de pastas e diretórios em que se encontra algum **recurso** (ou arquivo) desejado.
- a **busca** e o **identificador** são atributos opcionais que permitem o envio de informações ao documento acessado e o acesso a posições específicas, respectivamente.

Entretanto, ao acessar um site, nem todas essas características precisam ser informadas. Observe o exemplo a seguir: [https://biblioteca-virtual.com/uk](https://biblioteca-virtual.com/uk)

Nesse exemplo, podemos observar que o protocolo utilizado é o **HTTPS**, ou seja, o recurso acessado corresponde a um documento de hipertexto que foi acessado em uma conexão segura.

Para acessar um site, informar o protocolo não é obrigatório. Observe o domínio acessado: **biblioteca-virtual.com.** Veja que a porta não é informada; o navegador entende que, ao acessar o protocolo HTTPS, a porta de acesso ao servidor é a 443. Por fim, o endereço informado apresenta o caminho **uk**, e isso indica que os arquivos daquele site estão disponíveis em um diretório denominado **uk**.

# **Como funciona um site?**

[![](https://ampli-images.s3.amazonaws.com/production/9b4fe12b-4dc6-4b1c-9b92-287f54c93ddc/original)](https://ampli-images.s3.amazonaws.com/production/9b4fe12b-4dc6-4b1c-9b92-287f54c93ddc/original)

Um site pode ser considerado um documento de hipertexto que pode ser acessado a partir de um navegador. Para que um site seja acessado por um cliente (e/ou um usuário), ele deve estar disponibilizado em um computador que fique, o tempo todo, conectado à internet, a fim de permitir que outros dispositivos o acessem. A esse computador remoto dá-se o nome de servidor web (figura abaixo). Um servidor é um dispositivo que fornece algum serviço. No caso do servidor web, esse computador fornece o serviço de hospedagem de documentos web.

[![](https://ampli-images.s3.amazonaws.com/production/d0989671-0ce5-44f6-9c79-55d9d0f71941/original)](https://ampli-images.s3.amazonaws.com/production/d0989671-0ce5-44f6-9c79-55d9d0f71941/original)

Usuário acessando um site hospedado em um servidor remoto. Fonte: Shutterstock.

Na teoria, seria possível hospedar um site em seu próprio computador apenas instalando um _software_ servidor web e adquirindo um domínio e um endereço de IP fixo. Entretanto, a configuração desses sistemas é um pouco complexa e, a depender da quantidade de acessos ao site, pode tornar o uso de seu computador inviável. Em geral, para se colocar um site no ar, é preciso adquirir um domínio e alugar um servidor de hospedagem.

______

**📝 Exemplificando**

No Brasil, o departamento responsável pelo registro e pela manutenção de nomes de domínios com terminação “**.br**” é o Registro.br. Em geral, a aquisição de um domínio é cobrada anualmente e deve ser renovada enquanto o desenvolvedor desejar manter o nome de domínio.

______

Entretanto, antes de se adquirir um domínio, é preciso conhecer os conceitos que envolvem o desenvolvimento de um site.

______

**💭 Reflita**

Antigamente, os endereços de site eram precedidos pela combinação de letras **www** (um acrônimo para _world wide web_ ou, na tradução, “rede mundial de computadores”), como: www.google.com.br. Nos dias de hoje, esse mesmo site pode ser acessado sem o **www**: google.com.br. Reflita sobre os motivos disso.

______

# **Programação para WEB**

[![](https://ampli-images.s3.amazonaws.com/production/1d0988f3-c2b1-448c-8b00-b14c0cdc238f/original)](https://ampli-images.s3.amazonaws.com/production/1d0988f3-c2b1-448c-8b00-b14c0cdc238f/original)

O desenvolvimento web consiste na construção de documentos que podem ser acessados a partir de _websites._ Na prática, o desenvolvimento _web_ utiliza linguagens próprias para a construção de documentos: linguagens de marcação de hipertexto, de estilo e até mesmo de programação para construção de páginas _web_ dinâmicas. Em geral, as linguagens de desenvolvimento web podem ser classificadas como linguagens _back-end_ e linguagens _front-end_.

Linguagens _back-end_ são aquelas que são executadas diretamente no servidor. Elas podem ser utilizadas, por exemplo, para gerar uma página dinâmica que será enviada ao browser. São exemplos de linguagem back-end: PHP (PHP: _Hypertext Preprocessor_) e ASP (_Active Server Pages_). Já as linguagens _front-end_ são aquelas executadas diretamente no navegador do cliente, como, JavaScript, CSS (_Cascading Style Sheets_) e HTML (_HyperText Markup Language_). A figura abaixo ilustra algumas das principais linguagens de desenvolvimento web.

[![](https://ampli-images.s3.amazonaws.com/production/a1ffa0b2-40ff-4540-94c7-4c67fd4b67f9/original)](https://ampli-images.s3.amazonaws.com/production/a1ffa0b2-40ff-4540-94c7-4c67fd4b67f9/original)

Linguagens de desenvolvimento web. Fonte: Shutterstock.

No desenvolvimento de uma página web, a primeira linguagem que se deve compreender é o HTML.

# **Hypertext Markup Language (HTML)**

[![](https://ampli-images.s3.amazonaws.com/production/be445326-010c-40e1-bd58-436d8c186c92/original)](https://ampli-images.s3.amazonaws.com/production/be445326-010c-40e1-bd58-436d8c186c92/original)

HTML é um acrônimo para _HyperText Markup Language_ ou, na tradução, “linguagem de marcação de hipertexto”. O HTML fornece conjuntos de códigos que permitem a estruturação de uma página de internet que os navegadores conseguem interpretar e exibir o documento formatado de forma compreensiva ao usuário.

# **Versionamento da linguagem HTML e suas diferenças**

[![](https://ampli-images.s3.amazonaws.com/production/177275d0-539c-4914-95c5-a83f31d19389/original)](https://ampli-images.s3.amazonaws.com/production/177275d0-539c-4914-95c5-a83f31d19389/original)

A linguagem HTML foi oficialmente proposta no início dos anos 1990 pelo cientista da computação Tim Berners-Lee, enquanto trabalhava no CERN (_Conseil Européen pour la Recherche Nucléaire_ – Conselho Europeu de Pesquisa Nuclear). Tim Berners-Lee se inspirou na linguagem SGML (_Standard Generalized Markup Language)_ e ainda foi idealizador do conceito WWW (_World Wide Web_).

Inicialmente, o **HTML** foi construído para facilitar a comunicação entre colaboradores do CERN, entretanto, sua popularidade cresceu tanto que, em 1991, foi disponibilizado para o público.

[![](https://ampli-images.s3.amazonaws.com/production/4e5f649f-ff81-4bb2-9cae-4719c78a0f46/original)](https://ampli-images.s3.amazonaws.com/production/4e5f649f-ff81-4bb2-9cae-4719c78a0f46/original)

Linha do tempo da linguagem HTML. Fonte: Elaborado pelo autor.

Em 1995, a versão 2.0 do HTML foi publicada por Berners-Lee e um grupo de desenvolvedores. O **HTML 2.0** surgiu como um esforço para se criar uma especificação que permitisse interoperabilidade entre diversas implementações do HTML.

Nos anos seguintes, o HTML passou a ser uma recomendação oficial do W3C (_World Wide Web Consortium_), logo, iniciaram o desenvolvimento da terceira versão do HTML. Entretanto, a nova versão trouxe tantas diferenças em relação ao HTML 2.0 que tiveram problemas na implantação da proposta. Diante disso, os desenvolvedores decidiram abandonar a versão 3.0 e iniciar o desenvolvimento de uma nova versão, denominada **HTML 3.2**, oficialmente lançada em 1997.

O **HTML 3.2** trouxe uma série de novos recursos, como a possibilidade de inserção de tabelas e de texto ao redor de imagens.

Em dezembro de 1999, o W3C propôs oficialmente a versão **HTML 4.01**. Essa versão trouxe novos recursos com suporte a frames e tornou obsoletas algumas tags das versões anteriores do HTML. A quarta versão do HTML trazia recursos considerados revolucionários na época, como suporte a linguagens de scripts e a folhas de estilo em cascata. Nos anos seguintes, a W3C ainda propôs uma integração entre HTML e XML (_eXtensible Markup Language_), que ficou conhecida como XHTML (_eXtensible Hypertext Markup Language)_, visando à construção de documentos que fossem XMLs válidos.

A versão **HTML5** veio apenas em 2014, trazendo uma série de novos recursos que visavam, principalmente, à simplificação da sintaxe da linguagem. HTML5 trouxe suporte a inserções de áudio e vídeo diretamente no HTML, além de suporte a imagens vetoriais, como o formato SVG (_Scalable Vector Graphics)_.

# **Elementos básicos**

[![](https://ampli-images.s3.amazonaws.com/production/7f898b6a-7009-4924-9950-59811682e712/original)](https://ampli-images.s3.amazonaws.com/production/7f898b6a-7009-4924-9950-59811682e712/original)

HTML é fundamentado no conceito das chamadas _tags_ (marcações), que são códigos especiais inseridos entre parênteses angulares, ou seja, os sinais de < (menor que) e > (maior que). As _tags_ podem ser do tipo simples ou composto (MARIANO; DE MELO-MINARDI, 2017).

- _tag_ simples:

[![](https://ampli-images.s3.amazonaws.com/production/23a4c95f-8972-4fd6-997d-0016b6f68e59/original)](https://ampli-images.s3.amazonaws.com/production/23a4c95f-8972-4fd6-997d-0016b6f68e59/original)

- _tag_ composta:

[![](https://ampli-images.s3.amazonaws.com/production/c9ca8c87-b711-47ab-adc3-b77305dea5de/original)](https://ampli-images.s3.amazonaws.com/production/c9ca8c87-b711-47ab-adc3-b77305dea5de/original)

As _tags_ compostas são constituídas de uma declaração de abertura, do conteúdo que se deseja inserir e, por fim, de uma declaração de fechamento </exemplo-de-_tag_-composta>, que se distingue da declaração de abertura apenas pela barra inserida antes do nome da tag. Por outro lado, as tags simples não requerem uma declaração de fechamento.

As _tags_ podem ser personalizadas a partir da inserção de atributos, que recebem valores, geralmente, declarados entre aspas, da seguinte forma:

[![](https://ampli-images.s3.amazonaws.com/production/94932fa8-aa99-49c6-991d-4d23bc1a4d98/original)](https://ampli-images.s3.amazonaws.com/production/94932fa8-aa99-49c6-991d-4d23bc1a4d98/original)

Pode-se, ainda, inserir uma _tag_ dentro de outra _tag_. Nesse caso, a tag no interior é denominada como _tag_ filha. Observe:

[![](https://ampli-images.s3.amazonaws.com/production/2e8167da-6b20-4792-a02f-c9375eb9e22e/original)](https://ampli-images.s3.amazonaws.com/production/2e8167da-6b20-4792-a02f-c9375eb9e22e/original)

Neste caso, a _tag_ pai possui três _tags_ filhas. A menos que especificado, as _tags_ filhas herdam regras de formatação aplicadas à _tag_ pai. Não há limites na quantidade de _tags_ embutidas em outras _tags_:

[![](https://ampli-images.s3.amazonaws.com/production/ec2dfef6-2215-4aca-a8a4-0023039fa3fa/original)](https://ampli-images.s3.amazonaws.com/production/ec2dfef6-2215-4aca-a8a4-0023039fa3fa/original)

Em geral, costuma-se inserir tabulações (_tab_) para indicar que uma tag está contida dentro de outra. Isso é denominado indentação, e indentar o código não é obrigatório em HTML, entretanto, um código bem indentado facilita a leitura e, portanto, constitui em uma boa prática de desenvolvimento de códigos.

Páginas HTML devem ser salvas com a terminação “.html”. Em geral, denominamos a primeira página com o nome “_index_.html” (na tradução para o português: “índice”).

______

**📝 Exemplificando**

Documentos web podem ser construídos utilizando-se simples editores de texto, como o Bloco de Notas _(Window_s) ou o _Gedit (Linux_). Há desenvolvedores que preferem utilizar editores de terminal de linha de comando, como **vi** ou **nano**. Há, ainda, editores com recursos personalizados para desenvolvimento de códigos, como a indicação de linhas e o _syntax highligh_t, que é quando o editor colore palavras e blocos de código de acordo com a função delimitada pela linguagem utilizada. Como exemplo desses editores, podemos citar o _Notepad++,_ o _Visual Studio Code_ e o _Sublime Text_ (figura abaixo).

A escolha do editor depende da escolha pessoal do desenvolvedor.

[![](https://ampli-images.s3.amazonaws.com/production/907349ae-b709-42e9-9a3d-cce356f5d449/original)](https://ampli-images.s3.amazonaws.com/production/907349ae-b709-42e9-9a3d-cce356f5d449/original)

Exemplo de página construída usando Subline Text. Fonte: captura de tela do Sublime Text elaborada pelo autor.

# **“Olá, Mundo!”: Criando sua primeira página HTML**

[![](https://ampli-images.s3.amazonaws.com/production/2b6fb65d-75de-4eef-94dd-aedab62cce55/original)](https://ampli-images.s3.amazonaws.com/production/2b6fb65d-75de-4eef-94dd-aedab62cce55/original)

Agora que você foi introduzido aos conceitos básicos do HTML, vamos começar a criar nossa primeira página de internet.

[![](https://ampli-images.s3.amazonaws.com/production/ec4e7b78-0563-4dcc-969d-05ff72874f97/original)](https://ampli-images.s3.amazonaws.com/production/ec4e7b78-0563-4dcc-969d-05ff72874f97/original)

Minha primeira página. Fonte: Elaborado pelo autor.

Você pode, também, copiar o código em um bloco de notas, salvá-lo como “_index_.html” e abri-lo em um navegador. Você verá a seguinte página:

[![](https://ampli-images.s3.amazonaws.com/production/e0ff1cd6-6bb2-49e5-aba4-b7fa9fd1421e/original)](https://ampli-images.s3.amazonaws.com/production/e0ff1cd6-6bb2-49e5-aba4-b7fa9fd1421e/original)

Meu primeiro documento web exibido no navegador Chrome. Fonte: Captura de tela do navegador Chrome elaborada pelo autor.

Agora, vamos analisar o que é realizado para cada linha de código:

1. <!_DOCTYPE_ html>

Na primeira linha, vemos a declaração do tipo de documento; isso informa ao navegador que o documento em questão se trata de uma página web que usa HTML. Essa declaração indica, ainda, que se trata de uma página que usa HTML5. Outras versões do HTML utilizam declarações diferentes. A declaração do HTML 4.01 é feita da seguinte forma:

[![](https://ampli-images.s3.amazonaws.com/production/72eb6c01-4b73-4549-8130-f74cea2b8960/original)](https://ampli-images.s3.amazonaws.com/production/72eb6c01-4b73-4549-8130-f74cea2b8960/original)

A tag <html> aparece a seguir. Todo o conteúdo da página HTML deve ser inserido dentro dessa tag, por isso, ela é fechada apenas na última linha.

2. html>

A _tag_ <_head>_ deve conter informações do cabeçalho da página, indicando seus itens de configuração. Os conteúdos inseridos aqui não são exibidos no corpo da página.

3.   <_head_>

A _tag_ <_title_> permite a configuração do título que aparecerá no navegador (figura abaixo).

4. <_title_>Minha primeira página</_title_>

[![](https://ampli-images.s3.amazonaws.com/production/cfea5b02-4491-4798-937e-1b2d7063f0aa/original)](https://ampli-images.s3.amazonaws.com/production/cfea5b02-4491-4798-937e-1b2d7063f0aa/original)

Título. Captura de tela do navegador Chrome elaborada pelo autor.

A _tag_ <_meta_> permite a inserção de metadados na página (SILVA, 2018). Neste exemplo, a _tag_ meta recebe o atributo _charse_t, que, por sua vez, recebe o valor utf-8 (8-bit _Unicode Transformation Format_). Esse atributo altera a codificação de caracteres na página e permite que seu site tenha palavras com acento.

5. <_meta charset_="utf-8">

______

🔁 Assimile

A _tag meta_ é inserida dentro da _tag_ <_hea_d>; ela tem múltiplos propósitos e funcionalidades, em geral, relacionados a metadados da página. Observe algumas variações dessa _tag_:

- _meta name_: recebe os metadados do documento na forma de pares nome/valor. Exemplo:

[![](https://ampli-images.s3.amazonaws.com/production/bccdb5c2-f4f2-4e92-b420-8b0645894de8/original)](https://ampli-images.s3.amazonaws.com/production/bccdb5c2-f4f2-4e92-b420-8b0645894de8/original)

- _meta_ http-equiv=_refresh_: atualiza a página após um determinado número de segundos.

[![](https://ampli-images.s3.amazonaws.com/production/f4489417-69d6-4f88-997e-4f884f5b2816/original)](https://ampli-images.s3.amazonaws.com/production/f4489417-69d6-4f88-997e-4f884f5b2816/original)

- _meta charse_t: declaração de codificação de caracteres do documento. Exemplo:

[![](https://ampli-images.s3.amazonaws.com/production/3fe50e82-f6e3-41f6-8fb3-c4f9a7b236e0/original)](https://ampli-images.s3.amazonaws.com/production/3fe50e82-f6e3-41f6-8fb3-c4f9a7b236e0/original)

A _tag_ <_head_> é fechada na linha 6; em seguida, a _tag_ <body> é aberta. Essa _tag_ permite a inserção do conteúdo que será exibido no corpo da página.

6. </_head_>

7. <_body_>

A _tag_ <p> indica a inserção de parágrafos.

8. <p>Olá mundo!</p>

Por fim, as _tags_ <_body_> e <html> são fechadas. Todas as _tags_ compostas devem ser fechadas.

9. </_body_>

10.</html>

# **Parágrafo e títulos**

[![](https://ampli-images.s3.amazonaws.com/production/57e8dede-bf2e-4feb-b490-f252f3f8b927/original)](https://ampli-images.s3.amazonaws.com/production/57e8dede-bf2e-4feb-b490-f252f3f8b927/original)

No exemplo descrito anteriormente, conhecemos algumas _tags_ usadas para inserção de textos, como a _tag_ <p>. Agora, observe a figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/daa9bbf2-2765-408f-818a-b54dcad3adc0/original)](https://ampli-images.s3.amazonaws.com/production/daa9bbf2-2765-408f-818a-b54dcad3adc0/original)

Estrutura de uma página e tags de texto. Fonte: Elaborado pelo autor.

Nessa figura, vemos a estrutura de uma página, além de _tags_ utilizadas para inserção de parágrafos e títulos. A principal diferença entre elas está no tamanho da fonte. Títulos podem ser inseridos por meio das _tags_ <h1> a <h6>, sendo <h1> a maior e <h6> a menor (veja abaixo).

[![](https://ampli-images.s3.amazonaws.com/production/6b7e6a5e-1df5-45c2-a47f-6bc34275a803/original)](https://ampli-images.s3.amazonaws.com/production/6b7e6a5e-1df5-45c2-a47f-6bc34275a803/original)

Tags relacionadas a títulos. Fonte: Elaborado pelo autor.

Agora que você aprendeu os fundamentos do HTML, vamos fixar os conhecimentos sobre essa linguagem e iniciar o desenvolvimento de uma página web. Mãos à obra!

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

No início da aula, você foi desafiado a solucionar este problema ocasionado pelo Código 1.1: no _Internet Explorer_ os acentos e cedilha foram trocados por outros caracteres, dificultando a leitura do texto proposto.

A solução para isso seria declarar a codificação usada:

[![](https://ampli-images.s3.amazonaws.com/production/3bd50d5f-7544-43bb-94fd-f31f7eb47688/original)](https://ampli-images.s3.amazonaws.com/production/3bd50d5f-7544-43bb-94fd-f31f7eb47688/original)

Página HTML para comercializar planos de internet. Fonte: Elaborado pelo autor.

O resultado seria este:

[![](https://ampli-images.s3.amazonaws.com/production/a4ea4f64-866f-420f-9c49-c95291611229/original)](https://ampli-images.s3.amazonaws.com/production/a4ea4f64-866f-420f-9c49-c95291611229/original)

UTF-8 permite o uso de acentos. Fonte: Captura de tela do Internet Explorer elaborada pelo autor.

A codificação UTF-8 permite a inserção de caracteres como acentos e cedilha. Alguns navegadores conseguem identificar automaticamente a codificação usada, mas outros não, portanto, é recomendado, sempre, a inserção do código:

[![](https://ampli-images.s3.amazonaws.com/production/48d48b57-43af-4af1-a631-5a674bbff096/original)](https://ampli-images.s3.amazonaws.com/production/48d48b57-43af-4af1-a631-5a674bbff096/original)